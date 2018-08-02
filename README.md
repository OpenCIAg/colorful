# OpenCIAg | ciag-colorful

[![Build Status](https://travis-ci.org/OpenCIAg/colorful.svg?branch=master)](https://travis-ci.org/OpenCIAg/colorful)

[![Maintainability](https://api.codeclimate.com/v1/badges/acab5c036cce9af7f29f/maintainability)](https://codeclimate.com/github/OpenCIAg/colorful/maintainability)

[![Test Coverage](https://api.codeclimate.com/v1/badges/acab5c036cce9af7f29f/test_coverage)](https://codeclimate.com/github/OpenCIAg/colorful/test_coverage)

[![npm version](https://badge.fury.io/js/ciag-colorful.svg)](https://badge.fury.io/js/ciag-colorful)

## Install
```shell
npm install ciag-colorful
```

## Usage example with Angular

### Add the service
```ts
import { NgModule } from '@angular/core';
import { ColorService } from 'ciag-colorful';
import { PalleteBasedColorGenerator } from 'ciag-colorful/generator';
import { PalleteFactory, NEBULAR_CORPORATE } from 'ciag-colorful/pallete';

const palleteFactory = new PalleteFactory();
const pallete = palleteFactory.makeFromArray(NEBULAR_CORPORATE);

@NgModule({
    providers: [{
        provide: ColorService,
        useValue: new ColorService(new PalleteBasedColorGenerator(pallete,0.3))
    ]}
})
export class AppModule{}
```

### Use the service
```ts
import { Component } from '@angular/core';
import { ColorService } from 'ciag-colorful';

@Component({
    selector: 'colorful-component',
    templateUri: './colorful-component.html',
})
export class ColorfulComponent {

    constructor(
        private colorService: ColorService,
    ) {
        this.colorService.makeColor();
        //make a new color
        this.colorService.makeColor();

        this.colorSerice.makeColor('unique');
        //make the same color
        this.colorSerice.makeColor('unique');
    }

}

```

