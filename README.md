# Angular Playstation Store

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.1.2.

## Creating Project
Run `ng new angular-playstation-store` `Y` `CSS`
Open the `.editorconfig` file and change the line `indent_style = tab`

Open the `app.component.html` file, delete all content leaving only the `<router-outlet>` tag

Run `ng g c pages/home` command to create new page/component

Run `ng g c components/card` command to create new component

Run `ng g c components/menu-bar` command to create new component

As we will not work with tests, it excludes the `*spec.ts` files

Open `app.component.html` file and add

    <app-menu-bar></app-menu-bar>
    <app-home></app-home>
    <router-outlet></router-outlet>

Open the `styles.css` file and add `CSS Reset`

    * {
      padding: 0;
      margin: 0;
      border: 0;
      box-sizing: border-box;
    }


Also add `Gradient background`


    body {
      background: rgb(2,0,36);
      background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,9,121,1) 35%, rgba(9,9,121,1) 100%);
    }

Open the `home.component.html` file and add the code

    <div class="home__container">
      <app-card></app-card>
    </div>

Open the  `home.component.css`  file and add the code

    .home__container {
      width: 90%;
      margin: auto;
      padding: 50px;
      display: flex;

      justify-content: space-around;
      align-items: baseline;
      flex-wrap: wrap;
    }

Open the `menu-bar.component.html` file and add the code

    <div class="menu-bar__container">
      <div class="menu-bar__logo">
        <img
          src="assets/ps-logo.png"
          alt="Playstation Logo"
          srcset=""
          width="140px" height="32px"
        >
      </div>
      <div class="menu-bar__item">
        <ul>
          <li><a href="">YOUTUBE</a></li>
          <li><a href="">LINKEDIN</a></li>
          <li><a href="">GITHUB</a></li>
        </ul>
      </div>
    </div>
Open the `menu-bar.component.css` file and add the code

    .menu-bar__container {
      display: flex;
      flex-direction: row;
      position: fixed;
      z-index: 999;
      background-color: #fff;
      height: 40px;
      box-shadow: 0px 0px 6px 0px rgba(0,0,0,0.5)
    }

    .menu-bar__logo {
      margin-left: 30px;
      display: flex;
      align-items: center;
    }

    .menu-bar__item {
      display: flex;
      margin: auto;
      align-items: center;
    }

    .menu-bar__item > ul {
      display: flex;
      text-decoration: none;
      list-style-type: none;
    }

    .menu-bar__item > ul > li {
      padding: 5px;
      margin-right: 15px;
    }

    .menu-bar__item > ul > li > a {
      text-decoration: none;
      color: rgb(7,7,7);
      font-family: 'Segoe UI';
    }

    .menu-bar__item > ul > li > a:hover {
      color: blue;
      font-weight: bold;
    }

Run `ng g c components/card/card-label` command to create new sub-component

Run `ng g c components/card/card-pricing` command to create new sub-component

Open `card.component.html` file and add the code

    <a href="#" class="card__container">
      <img
        class="card__img"
        src="assets/bt-5.jpg"
        alt=""
        srcset=""
      >
      <app-card-label></app-card-label>
    </a>

Open `card.component.css` file and add the code

    .card__container {
      position: relative;
      border: 3px solid #3E4357;
      border-radius: 10px;
      width: 350px;
      height: 500px;

      display: flex;
      overflow: hidden;
      margin-top: 10px;
    }

    .card__img {
      min-width: 100%;
      min-height: 100%;
      transition: transform .8s;
    }

    .card__img:hover {
      transform: scale(1.1);
    }

Open `card-label.component.html` file and add the code

    <div class="card-label__container">
      <div class="card-label__content">
        <p>Exclusive</p>
      </div>
    </div>


Open `card-label.component.css` file and add the code

    .card-label__container {
      position: absolute;
      bottom: 90px;
      right: 0;
    }

    .card-label__content {
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #0D0D0D;
      color: #fff;
      font-size: 12px;
      font-family: 'Segoe UI';
      font-weight: bold;
      height: 40px;
      padding: 0px 50px;
    }

Open `card-label.component.ts` file and update the code

import { Component, Input, OnInit } from '@angular/core';

    @Component({
      selector: 'app-card-label',
      templateUrl: './card-label.component.html',
      styleUrls: ['./card-label.component.css']
    })
    export class CardLabelComponent implements OnInit {
      @Input()
      gameLabel:string=""
      constructor() { }
      ngOnInit(): void {
      }
    }

Open `card-label.component.html` file and update the code
  `<p>{{gameLabel}}</p>`

Open `card.component.html` file and update the code
  `<app-card-label gameLabel="Exclusive">
  </app-card-label>`

Open `card.pricing.component.html` file and add the code

    <div class="card-pricing__containet">
      <div class="card-pricing__title">
        <h3>Play it Now!</h3>
      </div>
      <div class="card-pricing__value">
        <div class="card-pricing__value__console">
          <span>|</span>
          <p>DIGITAL PS4</p>
        </div>
        <div class="card-pricing__value__money">
          <p class="game-price">R$ 129,99</p>
        </div>
      </div>
    </div>

Open `card.pricing.component.css` file and add the code

    .card-pricing__container {
      position: absolute;
      bottom: 0px;
      left: 0;

      display: flex;
      flex-direction: column;

      width: 100%;
      height: 70px;
      background-color: rgba(0,0,0,0.8);
      padding: 10px;
      color: antiquewhite;
      font-family: Calibri;
    }

    .card-pricing__title {
      margin-bottom: 3px;
    }

    .card-pricing__value {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
    }

    .card-pricing__value__console {
      display: flex;
      flex-direction: row;
    }

    .card-pricing__value__console > span {
      font-weight: bolder;
      color: aqua;
      margin-right: 10px;
    }

Open `card-pricing.component.ts` file and update the code

    import { Component, Input, OnInit } from '@angular/core';

    @Component({
      selector: 'app-card-pricing',
      templateUrl: './card-pricing.component.html',
      styleUrls: ['./card-pricing.component.css']
    })
    export class CardPricingComponent implements OnInit {

      @Input()
      gameType:string ="Digital PS4"
      @Input()
      gamePrice:string ="R$ 399,90"
      constructor() { }

      ngOnInit(): void {
      }
    }

Open `card.component.ts` file and update the code

    import { Component, Input, OnInit } from '@angular/core';

    @Component({
      selector: 'app-card',
      templateUrl: './card.component.html',
      styleUrls: ['./card.component.css']
    })
    export class CardComponent implements OnInit {

      @Input()
      gameCover:string = ""
      constructor() { }

      ngOnInit(): void {
      }
    }

`ng g c components/menu-bar/menu-bar-item`

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.
## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## 💻 Projeto

[See project in execution](https://angular-playstation-store.vercel.app/)
## References
[Gradient background](https://cssgradient.io/)

[Support Material](https://apple-cheek-322.notion.site/Material-para-Aula-ab520fdd264b420387e3e6fd203f700a)

[Project url on Felipe GitHub](https://github.com/felipeAguiarCode/angular-psn-store-clone)
## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
