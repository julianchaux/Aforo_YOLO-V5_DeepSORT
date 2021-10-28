# Control de Aforo usando YOLO-V5 y DeepSORT
Control de aforo utilizando YOLO V5 y Deep Sort.  Proyecto desarrollado en el marco del Diplomado en Machine Learning entre el SENA y la Universidad de Santander (UDES).

<div align="center">
<p>
<img src="Resultado1.gif" width="300"/> <img src="Resultado2.gif" width="300"/> <img src="Resultado3.gif" width="300"/> 
</p>
</div>


## Introducción

Este repositorio contiene un algoritmos de seguimiento de objetos de dos etapas. Las detecciones generadas por [YOLOv5](https://github.com/ultralytics/yolov5), una familia de arquitecturas y modelos de detección de objetos preentrenados en el conjunto de datos COCO, se pasan a un [algoritmo Deep Sort](https://github.com/ZQPei/deep_sort_pytorch) que rastrea los objetos. Puede rastrear cualquier objeto que su modelo Yolov5 haya sido entrenado para detectar.

## Fuentes de video para el seguimiento

El seguimiento puede tener diferentes fuentes de video:

```bash
python3 track.py --source ... --show-vid
```

- Video:  `--source file.mp4`
- Webcam:  `--source 0`
- RTSP stream:  `--source rtsp://170.93.143.139/rtplive/470011e600ef003a004ee33696235daa`
- HTTP stream:  `--source http://wmccpinetop.axiscam.net/mjpg/video.mjpg`

## Filtro de clases para el seguimiento

Por defecto, el rastreador sigue todas las clases de MS COCO.

Si sólo quiere rastrear personas:

```bash
python3 track.py --source 0 --yolo_weights yolov5/weights/crowdhuman_yolov5m.pt --classes 0
python track.py --source video.mp4 --show-vid --classes 0
```

Si desea realizar un seguimiento de un subconjunto de clases de MS COCO, añada su índice correspondiente después del indicador de clases:

```bash
python3 track.py --source 0 --yolo_weights yolov5s.pt --classes 16 17  # Sigue solo perros y gatos
```

## Cite

If you find this project useful in your research, please consider cite:

```latex
@misc{yolov5deepsort2020,
    title={Real-time multi-object tracker using YOLOv5 and deep sort},
    author={Mikel Broström},
    howpublished = {\url{https://github.com/mikel-brostrom/Yolov5_DeepSort_Pytorch}},
    year={2020}
}
```
