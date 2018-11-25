# BuggiesAndroid
This project is android application side of open source Buggies project for 6th Barama Fintech Hackathon.

This project consists of two main activities (LoginView and QrReadView) and fragments inside QrReadView Activity
Login page send login credentials to database and gets ApiKey for Future works.

<h1>Used technologies</h1>
<ul>
  <li>Model View Presenter Architecture for project code structure</li>
  <li>Retrofit for network requests</li>
  <li>ZXing Qr code reading library for qr reading</li>
  <li>Dokka for kotlin documentation</li>
  <li>Junit for Unit testing </li>
</ul>
All classes have their kotlin documentations. Dokka library generated JavaDoc automaticaly. For this aim need to do this: </br>
Go to Terminal at Android Studio and write following command</br>
<font color="bluew">gradlew dokka</font> </br>
This command will generate all Dacumentations as html format 


