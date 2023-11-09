# flutter_application_1

A new Flutter Web project.

## Getting Started
## NOTICE!!! You need first at all run 
```
flutter run -d chrome --web-renderer html

```
or
```
flutter build web --web-renderer canvaskit

```
This project it´s hosted an caprover instance.

A few steps to run this project:
1° Create some app in caprover (copy the name "")
2° Create captain-definition file in root project
```
 {
  "schemaVersion": 2,
  "dockerfilePath": "./Dockerfile"
 }

```
3° Create a .Dockerfile in root folder. To deoploy an FlutterWeb project in this case i m using httpd image, like that:
```
FROM httpd:alpine

COPY ./build/web /usr/local/apache2/htdocs/
	
EXPOSE 80
```
2° Create a folde called # .github, then subfolder # workflows inside file deploy.yaml
```
name: Flutter Web

on:
  push:
    branches:
      - main
      
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: subosito/flutter-action@v2
      with:
        channel: 'stable'
    - run: flutter pub get
    - run: flutter build web --web-renderer canvaskit

```
Now you can check action run on yor github project
Then in your cap rover instance into your app go to deployment section of your app and select the way to deploy this project
# The best way
![image](https://github.com/nadveos/increment/assets/94124026/5f8c9220-0217-4788-9a72-d52bfa92564f)


# 2nd way
![image](https://github.com/nadveos/increment/assets/94124026/e924a16b-b638-416b-b895-aef5ab1d97a0)


- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
