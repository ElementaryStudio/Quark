<!-- Logo -->
<p align="center">
  <a href="#">
    <img height="128" width="128" src="https://raw.githubusercontent.com/0xF6/Quark/master/icon/icon.png">
  </a>
</p>

<!-- Name -->
<h1 align="center">
  Elementary Quark Lib 🔅
</h1>
<p align="center">
  <a href="#">
    <img src="https://dev.azure.com/0xF6/Quark/_apis/build/status/0xF6.Quark?branchName=masterr">
    <img src="http://img.shields.io/:license-MIT-blue.svg">
    <img src="https://img.shields.io/github/release/0xF6/Quark.svg">
  </a>
  <a href="https://t.me/ivysola">
    <img src="https://img.shields.io/badge/Ask%20Me-Anything-1f425f.svg">
  </a>
</p>
<p align="center">
  <a href="#">
    <img src="https://forthebadge.com/images/badges/made-with-c-sharp.svg">
    <img src="https://forthebadge.com/images/badges/designed-in-ms-paint.svg">
    <img src="https://forthebadge.com/images/badges/ages-18.svg">
    <img src="https://ForTheBadge.com/images/badges/winter-is-coming.svg">
    <img src="https://forthebadge.com/images/badges/gluten-free.svg">
  </a>
</p>


Remark:       
  `This project is part of a closed project ElementarySandbox`    

### Install   
`dotnet add package Elementary.Quarks --version 1.4.0`


# API

### ElectricChange

Base parse:
```CSharp
var e = ElectricChange.Token.Parse("+(1/2)") 
// has return new object
{
  IsPositive: true,
  Value: "1/2"
}

e.ToString() // -> ["+(1/2)ℯ"]
```

### Quark


Support: `u d s c b t` quarks, and anti-quark `ū d̄ s̄ c̄ b̄ t̄`

Base parse:
```CSharp

var qList = Quark.Token.Parse("[u|u|d]") // uud a quark structure of proton

qList.First().ToString() // -> [u +(2/3)ℯ 2.01 MeV]


qList.First()
// ->
{
  Mass: new Energy(2.01, Energy.MegaElectronVolt),
  Symbol: 'u',
  Type: TopQuark,
  EChange: "+(2/3)"
}


// Also supported antiquark

var antiquark = Quark.Token.Parse("[-u]").First()

antiquark.ToString() // -> [ū +(2/3)ℯ 2.01 MeV]
antiquark.IsAnti() // -> True
```
