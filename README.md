# GAN_POC testing

```
python generate_train_data.py --file lisa.avi --num 400 --landmark-model shape_predictor_68_face_landmarks.dat

python tools/process.py --input_dir photos/original --operation resize --size 1024 --output_dir photos/original_resized

python tools/process.py --input_dir photos/landmarks --operation resize --size 1024 --output_dir photos/landmarks_resized

python tools/process.py --input_dir photos/landmarks_resized --b_dir photos/original_resized --operation combine --output_dir photos/combined

python tools/split.py --dir photos/combined

python pix2pix.py --mode train --output_dir face2face-model --max_epochs 200 --input_dir photos/combined/train --which_direction AtoB
```
