### 透明度测试

1.一般透明度测试需要三个Tag: "Queue" = "AlphaTest","IgnoreProjector" = "True","RenderType"= "TransparentCutout"

因为渲染顺序在Geometry效率更高所以第一个标签必不可少

第二个标签表明 不会受到透明Projector的影响

第三个标签是用于着色器替换功能



2.当透明度没达到阈值的时候就会被discard

3.如何判断?

 使用clip(float4) ,clip(float3),clip(float2),clip(float1) 函数

Equal to

```CG
void clip(float4 x)
if(any(x < 0))
	discard;
```





完整代码:

