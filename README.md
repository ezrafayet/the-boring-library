# The boring library 😈

This is a collection of clean json/yaml datasets of various sets of norms that are public yet painful to gather.

I hope you'll have fun using it !

## International norms of the library 🗺

* [x]   <a href="https://www.iso.org/standard/22109.html">ISO-639-1</a> ISO norm for languages codes (184 major languages)
* [x]   <a href="https://www.iso.org/standard/4767.html">ISO-639-2</a> ISO norm for languages codes (505 languages)
* [ ]   <a href="https://www.iso.org/standard/72482.html">ISO-3166-1</a> ISO norm for countries codes (249 countries)
* [ ]   <a href="https://www.iso.org/standard/72483.html">ISO-3166-2</a> ISO norm for countries-sub-regions codes
* [ ]   <a href="https://www.iso.org/standard/64758.html">ISO-4217</a> ISO norm for currencies codes
* [x]   <a href="https://www.itu.int/rec/T-REC-E.164">ITU-T-E.164</a> ITU-T norm for IDD / ISD codes
* [ ]   <a href="https://www.ilo.org/public/english/bureau/stat/isco/isco08/">ISCO-08</a> ISCO norm for occupations
* [ ]   <a href="https://ec.europa.eu/esco/portal/home">ESCO-2017</a> ESCO norms for occupations and skills
* [ ]   <a href="https://unstats.un.org/unsd/methodology/m49">UNSD-M49</a> Statistical norms for region and sub-region divisions

## Cross-sourced data 🧐

* [ ]   LANG Languages for each country
* [ ]   EUROPA European-union countries
* [ ]   UTC-OFFSETS UTS offsets

## Norm updates 📅

<table>
    <tr>
        <td style="text-align: center">Norm</td>
        <td style="text-align: center">Publication date</td>
        <td style="text-align: center">Last review</td>
        <td style="text-align: center">Next review</td>
        <td style="text-align: center">Generated here</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.iso.org/standard/22109.html">ISO-639-1</a></td>
        <td style="text-align: center">07-2002</td>
        <td style="text-align: center">2019</td>
        <td style="text-align: center">2024</td>
        <td style="text-align: center">05-04-2021</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.iso.org/standard/4767.html">ISO-639-2</a></td>
        <td style="text-align: center">11-1998</td>
        <td style="text-align: center">2016</td>
        <td style="text-align: center">2021</td>
        <td style="text-align: center">05-04-2021</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.iso.org/standard/72482.html">ISO-3166-1</a></td>
        <td style="text-align: center">2013</td>
        <td style="text-align: center">08-2020</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">-</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.iso.org/standard/72483.html">ISO-3166-2</a></td>
        <td style="text-align: center">2013</td>
        <td style="text-align: center">08-2020</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">-</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.iso.org/standard/64758.html">ISO-4217</a></td>
        <td style="text-align: center">2008</td>
        <td style="text-align: center">08-2015</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">-</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.itu.int/rec/T-REC-E.164">ITU-T-E.164</a></td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">11-2016</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">05-04-2021</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://www.ilo.org/public/english/bureau/stat/isco/isco08/">ISCO-08</a></td>
        <td style="text-align: center">2008</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">2028</td>
        <td style="text-align: center">-</td>
    </tr>
    <tr>
        <td style="text-align: center"><a href="https://unstats.un.org/unsd/methodology/m49">UNSD-M49</a></td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">-</td>
        <td style="text-align: center">-</td>
    </tr>
</table>

## Backward compatibility

For any breaking-change, backward compatibility is not guaranteed until alpha-1 release. Then backward compatibility will be standardized.

## Types 📏

### ISO-639-1 (184 major languages)

Data is a dictionary with key-value pairs:

```
{
    <key = 639-1-code>: {
        "639-1": string,
        "639-2": string,
        "language-name": {
            "native": string,
            "en": string
        }
    },
    ...
}
```

Sample:

```
{
    "ja": {
        "639-1": "ja",
        "639-2": "jpn",
        "family-name": "Japonic",
        "language-name": {
            "native": "日本語 (にほんご)", 
            "en": "Japanese"
        }
    }
}
```

Improvements to be done:

* Have languages names in all languages
* Add languages families
* Add information about each language being right-to-left or left-to-right

### ISO-639-2 (505 languages)

All languages from 639-1 are in 639-2.

Data-type is the same as above except keys are alpha-3 codes.

Sample:

```
{
    "zho": {
        "639-1": "zh", 
        "639-2": "zho", 
        "language-name": {
            "en": "chinese", 
            "fr": "chinois"
        }
    }
}
```

Improvements to be done are the same as above, plus:
* native names should be added

### ITU-T-E.164


Data is a dictionary with key-value pairs:

```
{
    <key = dialing-code>: alpha-2-country-code[],
}
```

Sample:

```
{
    ...
    "+372": ["EE"],
    "+373": ["MD"],
    "+374": ["AM", "QN"],
    ...
}
```
