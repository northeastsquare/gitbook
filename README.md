# cvat视频标注

1.类别：

```python
class_names=['car', 'truck', 'van', 'bus', 'pedestrian',
                'cyclist', 'tricyclelist', 'motorcyclist', 'barrowlist',
                'trafficcone', 'unknown_unmovable', 'unknown_movable',
                'triangle', 'trafficcone_fixed', 'trafficcone_other'
            ]
```

2.添加高度、截断、遮挡属性

3.标注视频，不是图片

4.需要编写json, 描述不同相机视频内，目标trackid的对应关系。 7个相机的每个20秒scene，即7个20秒视频，创建一个json文件，命名scene\_name\_trackid\_relation.json。trackid -1或缺失，代表该视频没有该目标

```json
{ 
    ["cam0_ts.mp4":-1, "cam1_ts.mp4":2, "cam2_ts.mp4":3, "cam3_ts.mp4":5, "cam4_ts.mp4":2, "cam5_ts.mp4":1, "cam6_ts.mp4":2],
    ["cam0_ts.mp4":2, "cam1_ts.mp4":-1, "cam2_ts.mp4":3]
}
```

5.关键点的顺序，从车上方，向下看，司机脚下为1，顺时针，1 2 3 4， 对应上方 5 6 7 8&#x20;

6.cvat 创建工程，内不同视频，创建不同task, task选对应的工程名称，创建的类别如上，属性添加高度

