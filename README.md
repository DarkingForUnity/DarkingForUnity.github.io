## Welcome to GitHub Pages

![DarkingForUnity's GitHub stats](https://github-readme-stats.vercel.app/api?username=DarkingForUnity&locale=cn)

### EditorTools
unity常用工具集合

#### 以下为目录链接：

##### [AES加密与解密](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/AES%E5%8A%A0%E5%AF%86%E4%B8%8E%E8%A7%A3%E5%AF%86)
* 采用AES对信息进行加密与解密

---

##### [Excel](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/Excel)
* 读取Excel 
	* [参考链接](https://www.cnblogs.com/XRTSDUT2008/p/6964856.html)

---

##### [Json](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/Json)
* Json读取与写入
	* 在editor界面对Json读取与写入；

对Json数据的操作可以分为：读取数据，操作数据，写入数据。<br> 
首先，是对数据的读取：
```C#
StreamReader sr = new StreamReader(Url, Encoding.UTF8);
string json = sr.ReadToEnd();
sr.Close();
if (json.Length > 0)
{
skills_ = JsonUtility.FromJson<Skills>(json);
}
```
读取文件采用从流中读取的方式，将json信息读取到本地对应的结构中。<br> 
将数据读取到本地后，就可以按照对一般数据操作的方式对数据进行操作。<br> 
操作完成后，将新的数据结构转换成json字符串，然后再写进json文件中<br> 
```C#
string json_ = JsonUtility.ToJson(skills, true);
File.WriteAllText(Url, json_, Encoding.UTF8);
```
<br>
<iframe width="100%" height="540" src="//player.bilibili.com/player.html?aid=971468433&bvid=BV17p4y1s7dC&cid=291770396&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
<br>

---

##### [MapEditor](https://github.com/HansenKing/EditorTools/tree/master/Assets/Tools_DK/MapEditor)
* 地图编辑器

<iframe width="100%" height="540" src="//player.bilibili.com/player.html?aid=416337634&bvid=BV1bV411q7Mu&cid=286047670&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

---

##### [QR Code](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/QR)
* 二维码生成器
	* Local：本地生成；
	* Network request ：请求草料二维码API ，返回二维码图片，需要网络

---


##### [brid-oid object鸟群算法](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/Birds)
* Boids 鸟群算法，全称 brid-oid object，类鸟对象
	从它的三条核心规则开始说起，克雷格·雷诺兹 Craig Reynolds 从观测群聚动物的过程中发现了群聚动物的行为有以下三个特征：

	* 分离 (Separation): 移动以避免拥挤整个集体 (steer to avoid crowding local flockmates)

	* 对齐 (Alignment): 朝着周围同伴移动的平均方向移动 (steer towards the average heading of local flockmates)

	* 聚集 (Cohesion): 朝着周围同伴的平均位置（质心）移动 (steer to move toward the average position of local flockmates)

---

##### [SpriteManage](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/SpriteManage)
* 精灵管理：
	* 检索场景中所有的空引用精灵图片；未激活spriterender组件的对象，未激活对象的spriterender；<br> 
	对于频繁改动的场景素材，有时候会留下一些空图片或者暂时保留，隐藏，最后要删除的图片对象。<br> 
	此脚本能帮助检索，识别以上对象，并进行一键清除组件或者清除对象。<br> 

	![image](/Image/CheckEmptySprite.png) <br>

	* 检索场景中引用到的精灵图集<br> 
	1、能够检索到场景中使用的所有图片的地址、图片存放文件夹地址以及打包图集名称，检测出是否包含未打包图片以及筛选未打包图片<br>
	2、在引用过多过杂乱的情况下，提供一键迁移功能，能够将图片一键迁移到目标文件夹，并将图片引用地址转移到新图片。

##### [三次贝塞尔曲线](https://github.com/DarkingForUnity/EditorTools/tree/master/Assets/Tools_DK/Json)
* 三次贝塞尔曲线
	* 设置三个点的坐标，通过贝塞尔曲线运算，在 LineRender 中插入坐标，使其拟合；<br> 
主要方法如下：<br>

```C#
void getBezier(int num)
    {
        line.positionCount = 0;
        Vector3[] vector3 = new Vector3[num+1];
        for (int i = 0; i <= num; i++)
        {
            float value = ((float)i / (float)num);
            vector3[i]= (1 - value * value) * tag0.transform.position + 2 * value * (1 - value) * tag1.transform.position + value * value * tag2.transform.position;
            //Debug.Log(vector3[i]+"   "+ value.ToString("")+"  "+ num+ "  " + i);
        }
        line.positionCount = vector3.Length;
        line.SetPositions(vector3);
        for (int i = 0; i < vector3.Length; i++)
        {
            line.SetPosition(i, vector3[i]);
        }
        
}
```
