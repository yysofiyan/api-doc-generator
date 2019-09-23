---
title: Pengembangan Apliksi Platform Kusus

language_tabs: # must be one of #
- Code

toc_footers:
  - <a href='#'>Yan Yan Sofiyan, M.Kom.</a>
  - Teknik Informatika-STMIK Sumedang
  - <a href='https://github.com/lord/slate'> Documentation Powered by Slate</a>
  - Copyright © 2018 


search: true
---

# Introductions

Sebelum berbicara lebih jauh tentang membuat CRUD Ionic Firebase, mari kita fahami dulu apa itu firebase.

<img class="picture-satu" src="images/mbaas.png" alt="firebase" />

*image source : [firebase.google.com](https://firebase.google.com/)*


[Firebase](https://firebase.google.com/) adalah [MBass](https://en.wikipedia.org/wiki/Mobile_backend_as_a_service)
(Backend as a Service) yang dimiliki oleh Google untuk mempemudah apps developer bisa fokus mengembangkan aplikasi tanpa harus memberikan effort yang besar untuk urusan backend.

Firebase itu terkait dengan Firebase Analytics, dan hal itu terbagi menjadi beberapa layanan yang disediakan oleh Firebase, antara lain `Develop`, `Grow`, dan `Earn`. Masing-masing layanan ini terbagi menjadi beberapa macam dan memiliki fungsi-fungsi tersendiri.

# Depelop

## Backend Services

1. **Realtime Database** :
Firebase menyediakan realtime database dan backend sebagai layanannya. Layanan ini menyediakan API yang digunakan untuk mensikronisasikan antara client dengan database yang disimpan dalam Firebase’s cloud.

2. **Authentication** :
Firebase Authentication merupakan layanan yang dapat mengotentikasi pengguna hanya menggunakan kode client-side. Hal ini mencakup user management system dimana pengguna dapat mengaktifkan otentikasi pengguna dengan email dan password dari login yang disimpan menggunakan Firebase.

3. **Hosting** :
Firebase Hosting merupakan layanan hosting website statis seperti CSS, HTML, JavaScript, dan lainnya yang tidak berubah secara dinamis. Layanan ini pertama kali diluncurkan pada tanggal 13 Mei 2014. Layanan mengirimkan file melalui Content Delivery Network (CDN) menggunakan HTTPS dan SSL.

4. **Storage** :
Firebase Storage merupakan layanan dimana developer dapat meng-upload dan men-download untuk aplikasi Firebase dengan aman, terlepas dari kualitas jaringan internet. Firebase Storage ini didukung oleh Google Cloud Storage.

5. **Cloud Messaging** :
Firebase Cloud Messaging merupakan solusi cross-platform dalam hal messaging dan notifikasi dari aplikasi di iOS, Android, maupun website tanpa biaya.

6. **Remote Config** :
Firebase Remote Config adalah layanan cloud yang memungkinkan developer dapat mengubah tampilan dan behavior dari aplikasi yang mereka kembangkan tanpa mengharuskan pengguna (user) untuk melakukan pembaruan aplikasi.

## App Quality Services

1. **Test Lab for Android** :
Layanan ini menyediakan infrastruktur berbasis Android untuk pengujian aplikasi Android. Secara otomatis, layanan ini melakukan berbagai macam tes *(testing)* dari aplikasi yang dikembangkan oleh *developer* di berbagai macam perangkat dan konfigurasi perangkat.

2. **Crash Reporting** :
Layanan ini dapat membuat laporan rinci dari *error-error* dalam aplikasi. Kesalahan *(error)* yang s serupa dikumpulkan jadi satu yang direpresentasikan dengan sistem *stack*. Karena menggunakan sistem stack, layanan ini memprioritaskan terhadap tingkat keparahan pada aplikasi tersebut.

# Grow

## Acquisition

1. **Dynamic Links** :
Merupakan URL cerdas yang secara dinamis dapat mengubah *behavior* untuk memberikan pengalaman terbaik di platform yang berbeda.

2. **Invites** :
Firebase Invites adalah sebuah layanan yang dapat mengirimkan *email* personal dan undangan SMS.

3. **AdWords** :
Firebase adalah SDK *(Software Development Kit)* dan alat analisis aplikasi dari Google. Bila kita menautkan Firebase dan AdWords, kita akan mendapatkan akses ke alat canggih yang membantu kita melihat bagaimana investasi AdWords kita mendorong pemasangan aplikasi dan tindakan dalam-aplikasi. 

## Re-Engagement

1. **Notifications** :
Firebase *Notifications* merupakan layanan gratis yang memungkinkan *user notifications* yang ditargetkan untuk para *developer* aplikasi mobile.

2. **App Indexing** :
Layanan ini memberikan kemudahan untuk aplikasi yang dibuat oleh *developer* supaya aplikasi tersebut dapat dikenal. Caranya adalah dengan menambahkan pengindeksan aplikasi dalam Google Search.

# Earn

## AdMob

AdMob adalah platform iklan seluler yang bisa digunakan untuk menghasilkan pendapatan dari aplikasi tersebut. Menggunakan AdMob dengan Firebase Analytics dapat memberikan tambahan kemampuan analytics dan data penggunaan aplikasi. Firebase terintegrasi dengan AdMob tanpa perlu mengubah konfigurasi AdMob yang ada.

# Start

## Create a CRUD Application with Ionic 3 and Firebase

# Setting Firebase
Membuat aplikasi baru di [Console firebase](https://console.firebase.google.com/u/0/) 

<img class="console-firebase" src="images/screencapture-console-firebase-google-u-0-2018-05-20-23_21_34.png" alt="console firebase"/> 

<img class="console-firebase" src="images/screencapture-console-firebase-google-u-0-2018-05-20-23_33_33.png" alt="console firebase"/> 

<img class="console-firebase" src="images/Screen Shot 2018-05-20 at 23.42.18.png" alt="console firebase"/> 

Silahkan isi form pop up yang muncul dengan nama aplikasi yang mau dibuat. Selanjutnya `Pilih Develop -> Database -> realtime database -> Mulai`

<img class="console-firebase" src="images/screencapture-console-firebase-google-u-0-project-crudfirebase-4171d-database-2018-05-20-23_52_55.png" alt="console firebase"/> 

Pilih `Mulai dalam mode pengujian/ start in test mode`, jadi Kita bisa CRUD ke database tanpa harus melakukan login dg firebase autentikasi.

<img class="console-firebase" src="images/screencapture-console-firebase-google-u-0-project-crudfirebase-4171d-database-2018-05-21-00_00_43.png" alt="console firebase"/> 

<img class="console-firebase" src="images/screencapture-console-firebase-google-u-0-project-crudfirebase-4171d-database-crudfirebase-4171d-data-2018-05-21-00_05_41.png" alt="console firebase"/> 

Persiapan pembuatan database di firebase sudah selesai. Selanjutnya ke tahap coding di ionic.

# Ionic 3 & Firebase

- New Project

`ionic start CrudFirebase blank`

- Install Plugin [AngularFire2](https://github.com/angular/angularfire2) 

`npm install angularfire2 firebase promise-polyfill --save`

`Plugin` inilah yang akan kita gunakan untuk bisa komunikasi dengan `firebase`. Untuk lebih jelas tentang documentasinya [AngularFire2](https://github.com/angular/angularfire2/blob/master/docs/ionic/v3.md)

Selanjutnya buka kembali web firebase kemudian `KlikAdd Firebase to your web app / Tambahkan Firebase ke aplikasi web anda`.

<img class="console-firebase" src="images/Screen Shot 2018-05-21 at 00.33.21.png" alt="console firebase"/>

<img class="console-firebase" src="images/Screen Shot 2018-05-21 at 00.36.52.png" alt="console firebase"/>

Kemudian copy dan paste `config` ke `app.firebaseconfig.ts.` `Create & Edit src/app/app.firebaseconfig.ts.`

> src / app /app.firebaseconfig.ts

```typescript
// Intialize Firebase
export var config = {
    apiKey: "AIzaSyBXJaSSEIhEcucvq2-8jbEfEhupzRQ9csU",
    authDomain: "crudfirebase-4171d.firebaseapp.com",
    databaseURL: "https://crudfirebase-4171d.firebaseio.com",
    projectId: "crudfirebase-4171d",
    storageBucket: "crudfirebase-4171d.appspot.com",
    messagingSenderId: "511669513572"
  };
```
Import 
`config.ts`,
`AngularFireModule` dan `AngularFireDatabase` 

di `module.ts`. Selanjutnya Edit `home.ts` & `home.html`

> src / app / app.module.ts

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { ErrorHandler, NgModule } from '@angular/core';
import { IonicApp, IonicErrorHandler, IonicModule } from 'ionic-angular';
import { SplashScreen } from '@ionic-native/splash-screen';
import { StatusBar } from '@ionic-native/status-bar';

import { MyApp } from './app.component';
import { HomePage } from '../pages/home/home';
import { config } from './app.firebaseconfig';

// import { AngularFireAuth } from 'angularfire2/auth';
import { AngularFireModule } from 'angularfire2';
import { AngularFireDatabase } from 'angularfire2/database';

@NgModule({
  declarations: [
    MyApp,
    HomePage
  ],
  imports: [
    BrowserModule,
    IonicModule.forRoot(MyApp),
    AngularFireModule.initializeApp(config)
  ],
  bootstrap: [IonicApp],
  entryComponents: [
    MyApp,
    HomePage
  ],
  providers: [
    StatusBar,
    SplashScreen,
    AngularFireDatabase,
    {provide: ErrorHandler, useClass: IonicErrorHandler}
  ]
})
export class AppModule {}
```

> /src/pages/home/home.ts

```javascript
export class HomePage {
	songs: Observable<any[]>;
```

```javascript
constructor(public navCtrl: NavController, public afDB: AngularFireDatabase) {
        this.songs = afDB.list('/songs').snapshotChanges().map(changes => {
            return changes.map(c => ({ key: c.payload.key, ...c.payload.val() }));
        });
    }

    add() {
        this.navCtrl.push("FormPage")
    }

    edit(song) {
        this.navCtrl.push("FormPage", {song: song})
    }

}

/* Pada `constructor` ada sebuah `service`
yang akan selalu `mendengarkan` apakah data di firebase berubah. Inilah yang menyebabkan database
di device selalu realtime, karena setiap database berubah device akan mengetahuinya. */
```

> /src/pages/home/home.html

```html
<ion-header>
  <ion-navbar>
    <ion-title>
      IONIC FIREBASE EXAMPLE
    </ion-title>
  </ion-navbar>
</ion-header>

<ion-content padding>
  <ion-list>
    <ion-item class="text" *ngFor="let song of songs | async" (click)="edit(song)">
      {{song.title}}
    </ion-item>
  </ion-list>

  <ion-fab bottom right>
      <button ion-fab (click) = "add()" >Add</button>
    </ion-fab>
</ion-content>
```
- Create Halaman `form`

`ionic generate page form`

Edit `form.ts` & Edit `form.html`

> /src/pages/form/form.ts

```typescript
import { Component } from '@angular/core';
import { IonicPage, NavController, NavParams } from 'ionic-angular';

import { AngularFireDatabase } from 'angularfire2/database';

@IonicPage()
@Component({
   selector: 'page-form',
   templateUrl: 'form.html',
})

export class FormPage {
    song: any = {
        id: '',
        title: '',
    }
    editsong:any;

    constructor(public navCtrl: NavController, public navParams: NavParams, public afDB: AngularFireDatabase) {
        this.editsong = this.navParams.get('song')
    }

    ionViewDidLoad() { 
        if (this.editsong) {
            this.song = this.editsong
        }
    }

    save() {
        if (this.editsong) {
            this.afDB.list('/songs/').update(this.editsong.key, {
                id : this.song.id,
                title : this.song.title
            }).then(()=>{
                console.log("update berhasil");
            }).catch(e=>console.log(e));
        } else {
            this.afDB.list('/songs/').push({
                id : this.song.id,
                title : this.song.title
            }).then(()=>{
                console.log("simpan data baru berhasil");
            });
        }

        this.navCtrl.pop();
    }

    deleteBook() {

    }

}

/*
Pada method ionViewDidLoad() kita lakukan 
pengecekan, apakah ada data song yang dikirimkan
dari homepage?. Jika memang ada berarti ini adalah proses edit. Jika tidak ada berarti proses create.

Begitupun dilakukan pengecekan saat mau save.
Apakah tambah data atau update. */
```

> /src/pages/form/form.html

```html
<ion-header>
    <ion-navbar>
    	<ion-title> {{ title }} </ion-title>
    </ion-navbar>
</ion-header>

<ion-content padding>
    <ion-list>
        <ion-item>
            <ion-label floating>id</ion-label>
            <ion-input type="judul" [(ngModel)] = "song.id" ></ion-input>
        </ion-item>
        <ion-item>
            <ion-label floating>Title</ion-label>
            <ion-input type="penerbit" [(ngModel)] = "song.title" ></ion-input>
        </ion-item>
        <ion-item text-center>
            <button ion-button round style="min-width: 200px; padding: 10px 16px" (click) = "save()">Save</button>
            <br/>
            <button ion-button round style="min-width: 200px; padding: 10px 16px" (click) = "deleteBook()">Delete</button>
        </ion-item>
    </ion-list>
</ion-content>
```

# Kesimpulan
<aside class="success">
Jadi salah satu library yang digunakan Ionic / Angular untuk komunikasi ke firebase adalah <code>angularfire2</code>, Library ini cukup handal untuk menangani proses-proses saat kita akan menggunakan fitur-fitur firebase.
</aside>

<img class="framework-tecnologi" src="images/frameworks-and-technologies.png" alt="framework-tecnologi"/>

# Referensi

- [Firebase Blog](https://www.firebase.com/blog/)
- [Firebase.google](https://firebase.google.com/)
- [Ionicframework](https://ionicframework.com/docs/v1/guide/preface.html)
- [Plugin Angularfire2](https://github.com/angular/angularfire2) 
- [Angular](https://angular.io/)
- [medium.com/realtime-database-pada-firebase-android](https://medium.com/@namakulinux/belajar-realtime-database-pada-firebase-android-9e016f9aa60f)

