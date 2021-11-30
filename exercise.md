### Compare two JSON objects:
```js
let obj1 = {name: "Person1", age: 5};
let obj2 = {age: 5, name: "Person1"};
// comparing these two obj using for..in
let equalFlag = "equal";   // variable to store equality result
for(let key in obj1) {
  // if any value doesn't match then not equal and stop loop
  if(obj1[key] !== obj2[key]) {
    equalFlag = "not equal";
    break;
  }
}
console.log("Given two objects are " + equalFlag);
```
- Output:
> Given two objects are equal

### Display flags in console
- Used https://restcountries.com/v3.1/all api and one country didn't have flag set so it has undefined value.
- I concatanated country flags so it will be easy to output as compared to printing each flag on different line.
```js
let xhr = new XMLHttpRequest();

xhr.open("GET", "https://restcountries.com/v3.1/all");

xhr.onload = function() {
  if(xhr.status >= 200 && xhr.status < 300) {
    let data = JSON.parse(this.responseText);
    let flags = "";
    for(let country of data) {
      flags += country.flag + " ";
    }
    console.log(flags);
  } else {
    console.log("Error");
  }
};

xhr.send();
```
- Output:
> 🇦🇫 🇸🇩 🇧🇮 🇲🇽 🇨🇺 🇷🇸 🇲🇨 🇧🇹 🇬🇾 🇬🇸 🇧🇦 🇧🇳 🇵🇰 🇰🇪 🇵🇷 🇸🇴 🇸🇯 🇸🇱 🇵🇫 🇦🇿 🇨🇰 🇵🇪 🇧🇻 🇲🇵 🇦🇴 🇨🇬 🇸🇸 🇲🇫 🇹🇷 🇦🇮 🇰🇳 🇦🇼 🇹🇨 🇹🇼 🇸🇪 🇱🇷 🇻🇪 🇻🇮 🇧🇲 🇦🇱 🇭🇰 🇱🇺 🇪🇷 🇨🇴 undefined 🇲🇳 🇾🇪 🇱🇧 🇦🇬 🇻🇳 🇵🇼 🇯🇪 🇹🇹 🇮🇱 🇧🇬 🇵🇹 🇬🇮 🇸🇲 🇸🇬 🇸🇽 🇸🇦 🇬🇭 🇲🇩 🇹🇩 🇦🇶 🇬🇧 🇵🇬 🇹🇫 🇺🇲 🇧🇿 🇰🇲 🇧🇫 🇫🇴 🇬🇳 🇮🇳 🇨🇼 🇹🇬 🇹🇳 🇧🇱 🇮🇩 🇫🇲 🇦🇹 🇹🇯 🇨🇩 🇾🇹 🇷🇪 🇷🇴 🇶🇦 🇱🇹 🇨🇳 🇳🇿 🇳🇫 🇲🇷 🇺🇿 🇫🇮 🇨🇲 🇭🇲 🇩🇲 🇮🇸 🇴🇲 🇲🇰 🇱🇮 🇪🇸 🇬🇷 🇵🇾 🇧🇭 🇳🇺 🇸🇳 🇲🇸 🇱🇻 🇹🇰 🇯🇵 🇨🇫 🇬🇦 🇮🇶 🇮🇲 🇲🇲 🇲🇪 🇳🇷 🇻🇺 🇫🇷 🇿🇼 🇵🇭 🇸🇰 🇦🇺 🇨🇮 🇮🇴 🇸🇿 🇷🇼 🇧🇯 🇻🇬 🇺🇬 🇮🇪 🇮🇷 🇸🇮 🇲🇱 🇨🇭 🇦🇸 🇺🇾 🇬🇺 🇸🇷 🇺🇦 🇨🇿 🇭🇳 🇼🇸 🇱🇦 🇨🇻 🇪🇹 🇧🇩 🇸🇭 🇧🇾 🇭🇷 🇰🇼 🇬🇫 🇲🇦 🇷🇺 🇪🇪 🇱🇰 🇳🇨 🇵🇱 🇲🇬 🇨🇷 🇸🇻 🇲🇴 🇦🇩 🇮🇹 🇳🇦 🇸🇨 🇵🇦 🇭🇹 🇦🇷 🇳🇪 🇲🇼 🇵🇳 🇩🇪 🇰🇮 🇸🇾 🇲🇭 🇭🇺 🇰🇾 🇩🇰 🇱🇨 🇧🇴 🇩🇯 🇿🇦 🇳🇬 🇸🇹 🇳🇮 🇬🇵 🇵🇲 🇪🇨 🇬🇱 🇬🇩 🇧🇸 🇨🇱 🇲🇾 🇹🇻 🇨🇽 🇸🇧 🇹🇿 🇰🇵 🇬🇼 🇽🇰 🇻🇦 🇳🇴 🇵🇸 🇨🇨 🇯🇲 🇪🇬 🇰🇭 🇲🇺 🇬🇲 🇬🇶 🇱🇸 🇲🇶 🇺🇸 🇪🇭 🇦🇪 🇲🇿 🇩🇿 🇿🇲 🇬🇹 🇰🇷 🇰🇬 🇹🇱 🇦🇽 🇯🇴 🇲🇹 🇨🇾 🇫🇰 🇰🇿 🇧🇼 🇻🇨 🇧🇧 🇹🇴 🇹🇭 🇧🇪 🇨🇦 🇬🇪 🇼🇫 🇫🇯 🇳🇱 🇦🇲 🇩🇴 🇬🇬 🇹🇲 🇳🇵 🇲🇻 🇱🇾 🇧🇷

### Display country details:
```js
let xhr = new XMLHttpRequest();

xhr.open("GET", "https://restcountries.com/v3.1/all");

xhr.onload = function() {
  if(xhr.status >= 200 && xhr.status < 300) {
    let data = JSON.parse(this.responseText);
    for(let country of data) {
      console.log(country.name.common + ", " + country.region + ", " + country.subregion + ", "
                + country.population);
    }
  } else {
    console.log("Error");
  }
};

xhr.send();
```
- Output:
> Afghanistan, Asia, Southern Asia, 2837743  
Sudan, Africa, Northern Africa, 43849269  
Burundi, Africa, Eastern Africa, 11890781  
Mexico, Americas, North America, 128932753  
Cuba, Americas, Caribbean, 11326616  
Serbia, Europe, Southeast Europe, 6908224  
Monaco, Europe, Western Europe, 39244  
Bhutan, Asia, Southern Asia, 771612  
Guyana, Americas, South America, 786559  
South Georgia, Antarctic, undefined, 30  
Bosnia and Herzegovina, Europe, Southeast Europe, 3280815  
Brunei, Asia, South-Eastern Asia, 437483  
Pakistan, Asia, Southern Asia, 220892331  
Kenya, Africa, Eastern Africa, 53771300  
Puerto Rico, Americas, Caribbean, 3194034  
Somalia, Africa, Eastern Africa, 15893219  
Svalbard and Jan Mayen, Europe, Northern Europe, 2562  
Sierra Leone, Africa, Western Africa, 7976985  
French Polynesia, Oceania, Polynesia, 280904  
Azerbaijan, Asia, Western Asia, 10110116  
Cook Islands, Oceania, Polynesia, 18100  
Peru, Americas, South America, 32971846  
Bouvet Island, Antarctic, undefined, 0  
Northern Mariana Islands, Oceania, Micronesia, 57557  
Angola, Africa, Middle Africa, 32866268  
Republic of the Congo, Africa, Middle Africa, 89561404  
South Sudan, Africa, Middle Africa, 11193729  
Saint Martin, Americas, Caribbean, 38659  
Turkey, Asia, Western Asia, 84339067  
Anguilla, Americas, Caribbean, 13452  
Saint Kitts and Nevis, Americas, Caribbean, 53192  
Aruba, Americas, Caribbean, 106766  
Turks and Caicos Islands, Americas, Caribbean, 38718  
Taiwan, Asia, Eastern Asia, 23503349  
Sweden, Europe, Northern Europe, 10353442  
Liberia, Africa, Western Africa, 5057677  
Venezuela, Americas, South America, 28435943  
United States Virgin Islands, Americas, Caribbean, 106290  
Bermuda, Americas, North America, 63903  
Albania, Europe, Southeast Europe, 2837743  
Hong Kong, Asia, Eastern Asia, 7500700 
Luxembourg, Europe, Western Europe, 632275  
Eritrea, Africa, Eastern Africa, 5352000  
Colombia, Americas, South America, 50882884  
Caribbean Netherlands, Americas, Caribbean, 25987  
Mongolia, Asia, Eastern Asia, 3278292  
Yemen, Asia, Western Asia, 29825968  
Lebanon, Asia, Western Asia, 6825442  
Antigua and Barbuda, Americas, Caribbean, 97928  
Vietnam, Asia, South-Eastern Asia, 97338583  
Palau, Oceania, Micronesia, 18092  
Jersey, Europe, Northern Europe, 100800  
Trinidad and Tobago, Americas, Caribbean, 1399491  
Israel, Asia, Western Asia, 9216900  
Bulgaria, Europe, Southeast Europe, 6927288  
Portugal, Europe, Southern Europe, 10305564  
Gibraltar, Europe, Southern Europe, 33691  
San Marino, Europe, Southern Europe, 33938  
Singapore, Asia, South-Eastern Asia, 5685807  
Sint Maarten, Americas, Caribbean, 40812  
Saudi Arabia, Asia, Western Asia, 34813867  
Ghana, Africa, Western Africa, 31072945  
Moldova, Europe, Eastern Europe, 2617820  
Chad, Africa, Middle Africa, 16425859  
Antarctica, Antarctic, undefined, 1000  
United Kingdom, Europe, Northern Europe, 67215293  
Papua New Guinea, Oceania, Melanesia, 8947027  
French Southern and Antarctic Lands, Antarctic, undefined, 400  
United States Minor Outlying Islands, Americas, North America, 300  
Belize, Americas, Central America, 397621  
Comoros, Africa, Eastern Africa, 869595  
Burkina Faso, Africa, Western Africa, 20903278  
Faroe Islands, Europe, Northern Europe, 48865  
Guinea, Africa, Western Africa, 13132792  
India, Asia, Southern Asia, 1380004385  
Curaçao, Americas, Caribbean, 155014  
Togo, Africa, Western Africa, 8278737  
Tunisia, Africa, Northern Africa, 11818618  
Saint Barthélemy, Americas, Caribbean, 4255  
Indonesia, Asia, South-Eastern Asia, 273523621  
Micronesia, Oceania, Micronesia, 115021  
Austria, Europe, Central Europe, 8917205  
Tajikistan, Asia, Central Asia, 9537642  
DR Congo, Africa, Middle Africa, 89561404  
Mayotte, Africa, Eastern Africa, 226915  
Réunion, Africa, Eastern Africa, 840974  
Romania, Europe, Southeast Europe, 19286123  
Qatar, Asia, Western Asia, 2881060  
Lithuania, Europe, Northern Europe, 2794700  
China, Asia, Eastern Asia, 1402112000  
New Zealand, Oceania, Australia and New Zealand, 5084300  
Norfolk Island, Oceania, Australia and New Zealand, 2302  
Mauritania, Africa, Western Africa, 4649660  
Uzbekistan, Asia, Central Asia, 34232050  
Finland, Europe, Northern Europe, 5530719  
Cameroon, Africa, Middle Africa, 26545864  
Heard Island and McDonald Islands, Antarctic, undefined, 0  
Dominica, Americas, Caribbean, 71991  
Iceland, Europe, Northern Europe, 366425  
Oman, Asia, Western Asia, 5106622  
North Macedonia, Europe, Southeast Europe, 2077132  
Liechtenstein, Europe, Western Europe, 38137  
Spain, Europe, Southern Europe, 47351567  
Greece, Europe, Southern Europe, 10715549  
Paraguay, Americas, South America, 7132530  
Bahrain, Asia, Western Asia, 1701583  
Niue, Oceania, Polynesia, 1470  
Senegal, Africa, Western Africa, 16743930  
Montserrat, Americas, Caribbean, 4922  
Latvia, Europe, Northern Europe, 1901548  
Tokelau, Oceania, Polynesia, 1411  
Japan, Asia, Eastern Asia, 125836021  
Central African Republic, Africa, Middle Africa, 4829764  
Gabon, Africa, Middle Africa, 2225728  
Iraq, Asia, Western Asia, 40222503  
Isle of Man, Europe, Northern Europe, 85032  
Myanmar, Asia, South-Eastern Asia, 54409794  
Montenegro, Europe, Southeast Europe, 621718  
Nauru, Oceania, Micronesia, 10834  
Vanuatu, Oceania, Melanesia, 307150  
France, Europe, Western Europe, 67391582  
Zimbabwe, Africa, Eastern Africa, 14862927  
Philippines, Asia, South-Eastern Asia, 109581085  
Slovakia, Europe, Central Europe, 5458827  
Australia, Oceania, Australia and New Zealand, 25687041  
Ivory Coast, Africa, Western Africa, 26378275  
British Indian Ocean Territory, Africa, Eastern Africa, 3000  
Eswatini, Africa, Southern Africa, 1160164  
Rwanda, Africa, Eastern Africa, 12952209  
Benin, Africa, Western Africa, 12123198  
British Virgin Islands, Americas, Caribbean, 30237  
Uganda, Africa, Eastern Africa, 45741000  
Ireland, Europe, Northern Europe, 4994724  
Iran, Asia, Southern Asia, 83992953  
Slovenia, Europe, Central Europe, 2100126  
Mali, Africa, Western Africa, 20250834  
Switzerland, Europe, Western Europe, 17500657  
American Samoa, Oceania, Polynesia, 55197  
Uruguay, Americas, South America, 3473727  
Guam, Oceania, Micronesia, 168783  
Suriname, Americas, South America, 586634  
Ukraine, Europe, Eastern Europe, 44134693  
Czechia, Europe, Central Europe, 10698896  
Honduras, Americas, Central America, 9904608  
Samoa, Oceania, Polynesia, 198410  
Laos, Asia, South-Eastern Asia, 7275556  
Cape Verde, Africa, Western Africa, 555988  
Ethiopia, Africa, Eastern Africa, 114963583  
Bangladesh, Asia, Southern Asia, 164689383  
Saint Helena, Ascension and Tristan da Cunha, Africa, Western Africa, 53192  
Belarus, Europe, Eastern Europe, 9398861  
Croatia, Europe, Southeast Europe, 4047200  
Kuwait, Asia, Western Asia, 4270563  
French Guiana, Americas, South America, 254541  
Morocco, Africa, Northern Africa, 36910558  
Russia, Europe, Eastern Europe, 144104080  
Estonia, Europe, Northern Europe, 1331057  
Sri Lanka, Asia, Southern Asia, 21919000  
New Caledonia, Oceania, Melanesia, 271960  
Poland, Europe, Central Europe, 37950802  
Madagascar, Africa, Eastern Africa, 27691019  
Costa Rica, Americas, Central America, 5094114  
El Salvador, Americas, Central America, 6486201  
Macau, Asia, Eastern Asia, 649342  
Andorra, Europe, Southern Europe, 77265  
Italy, Europe, Southern Europe, 59554023  
Namibia, Africa, Southern Africa, 2540916  
Seychelles, Africa, Eastern Africa, 98462  
Panama, Americas, Central America, 4314768  
Haiti, Americas, Caribbean, 11402533  
Argentina, Americas, South America, 45376763  
Niger, Africa, Western Africa, 24206636  
Malawi, Africa, Eastern Africa, 19129955  
Pitcairn Islands, Oceania, Polynesia, 56  
Germany, Europe, Western Europe, 83240525  
Kiribati, Oceania, Micronesia, 119446  
Syria, Asia, Western Asia, 17500657  
Marshall Islands, Oceania, Micronesia, 59194  
Hungary, Europe, Central Europe, 9749763  
Cayman Islands, Americas, Caribbean, 65720  
Denmark, Europe, Northern Europe, 5831404  
Saint Lucia, Americas, Caribbean, 183629  
Bolivia, Americas, South America, 11673029  
Djibouti, Africa, Eastern Africa, 988002  
South Africa, Africa, Southern Africa, 59308690  
Nigeria, Africa, Western Africa, 206139587  
São Tomé and Príncipe, Africa, Middle Africa, 219161  
Nicaragua, Americas, Central America, 6624554  
Guadeloupe, Americas, Caribbean, 400132  
Saint Pierre and Miquelon, Americas, North America, 6069  
Ecuador, Americas, South America, 17643060  
Greenland, Americas, North America, 56367  
Grenada, Americas, Caribbean, 112519  
Bahamas, Americas, Caribbean, 393248  
Chile, Americas, South America, 19116209  
Malaysia, Asia, South-Eastern Asia, 32365998  
Tuvalu, Oceania, Polynesia, 11792  
Christmas Island, Oceania, Australia and New Zealand, 2072  
Solomon Islands, Oceania, Melanesia, 686878  
Tanzania, Africa, Eastern Africa, 59734213  
North Korea, Asia, Eastern Asia, 25778815  
Guinea-Bissau, Africa, Western Africa, 1967998  
Kosovo, Europe, Southeast Europe, 1775378  
Vatican City, Europe, Southern Europe, 451  
Norway, Europe, Northern Europe, 5379475  
Palestine, Asia, Western Asia, 4803269  
Cocos (Keeling) Islands, Oceania, Australia and New Zealand, 544  
Jamaica, Americas, Caribbean, 2961161  
Egypt, Africa, Northern Africa, 102334403  
Cambodia, Asia, South-Eastern Asia, 16718971  
Mauritius, Africa, Eastern Africa, 1265740  
Gambia, Africa, Western Africa, 2416664  
Equatorial Guinea, Africa, Middle Africa, 1402985  
Lesotho, Africa, Southern Africa, 2142252  
Martinique, Americas, Caribbean, 378243  
United States, Americas, North America, 329484123  
Western Sahara, Africa, Northern Africa, 510713  
United Arab Emirates, Asia, Western Asia, 9890400  
Mozambique, Africa, Eastern Africa, 31255435  
Algeria, Africa, Northern Africa, 510713  
Zambia, Africa, Eastern Africa, 18383956  
Guatemala, Americas, Central America, 16858333  
South Korea, Asia, Eastern Asia, 51780579  
Kyrgyzstan, Asia, Central Asia, 6591600  
Timor-Leste, Asia, South-Eastern Asia, 1318442  
Åland Islands, Europe, Northern Europe, 29458  
Jordan, Asia, Western Asia, 10203140  
Malta, Europe, Southern Europe, 525285  
Cyprus, Europe, Southern Europe, 1207361  
Falkland Islands, Americas, South America, 2563  
Kazakhstan, Asia, Central Asia, 18754440  
Botswana, Africa, Southern Africa, 2351625  
Saint Vincent and the Grenadines, Americas, Caribbean, 110947  
Barbados, Americas, Caribbean, 287371  
Tonga, Oceania, Polynesia, 105697  
Thailand, Asia, South-Eastern Asia, 69799978  
Belgium, Europe, Western Europe, 11555997  
Canada, Americas, North America, 38005238  
Georgia, Asia, Western Asia, 3714000  
Wallis and Futuna, Oceania, Polynesia, 11750  
Fiji, Oceania, Melanesia, 896444  
Netherlands, Europe, Western Europe, 16655799  
Armenia, Asia, Western Asia, 2963234  
Dominican Republic, Americas, Caribbean, 10847904  
Guernsey, Europe, Northern Europe, 62999  
Turkmenistan, Asia, Central Asia, 6031187  
Nepal, Asia, Southern Asia, 29136808  
Maldives, Asia, Southern Asia, 540542  
Libya, Africa, Northern Africa, 6871287  
Brazil, Americas, South America, 212559409  



