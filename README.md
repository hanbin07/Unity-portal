# Unity-portal
## Portal , (Stencil buffer)

#### Unity allows you to view objects in the desired form 
#### (although they are not actually cut, you can use a stencil buffer to render only objects in the desired area)

#### Front: PortalPlane shader
#### Back: Spozar shader


하단의 코드로 빛의 세기, 각도 수정 가능
Spnzar shader를 수정해야함

```shader
fixed4 frag (v2f i) : SV_Target
			{
				float3 normal = normalize(i.normal);
				float3 lightDir = normalize(float3(15.0, 10.0, 10.0));
				float l = max(dot(lightDir, normal), 0.0);
				float4 texCol = tex2D(_MainTex, i.uv);
				fixed4 col = texCol * l + texCol * 0.95f;
				return col;
			}
```

