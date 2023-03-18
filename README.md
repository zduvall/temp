# temp

```js
const go = () => {
  const submitForm = () => {
    function toTitleCase(str) {
      return str.replace(/\w\S*/g, function (txt) {
        return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
      });
    }

    function rNum(max = 9) {
      return Math.floor(Math.random() * max) + 1;
    }

    function rNumS(length) {
      let res = '';
      for (let i = 0; i < length; i++) {
        res += rNum();
      }
      return res;
    }

    function rString(length, spaces = true) {
      let result = '';
      let letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz';
      if (spaces) letters += '        ';
      for (let i = 0; i < length; i++) {
        result += letters.charAt(rNum(letters.length));
      }
      return toTitleCase(result.trim());
    }

    const states = [
      'Alabama',
      'Alaska',
      'Arizona',
      'Arkansas',
      'California',
      'Colorado',
      'Connecticut',
      'Delaware',
      'Florida',
      'Georgia',
      'Hawaii',
      'Idaho',
      'Illinois',
      'Indiana',
      'Iowa',
      'Kansas',
      'Kentucky',
      'Louisiana',
      'Maine',
      'Maryland',
      'Massachusetts',
      'Michigan',
      'Minnesota',
      'Mississippi',
      'Missouri',
      'Montana',
      'Nebraska',
      'Nevada',
      'New Hampshire',
      'New Jersey',
      'New Mexico',
      'New York',
      'North Carolina',
      'North Dakota',
      'Ohio',
      'Oklahoma',
      'Oregon',
      'Pennsylvania',
      'Rhode Island',
      'South Carolina',
      'South Dakota',
      'Tennessee',
      'Texas',
      'Utah',
      'Vermont',
      'Virginia',
      'Washington',
      'West Virginia',
      'Wisconsin',
      'Wyoming',
    ];
    const state = states[Math.floor(Math.random() * states.length)];

    const ssl = `${rNumS(3)}-${rNumS(2)}-${rNumS(4)}`;
    const phone = `(${rNumS(3)}) ${rNumS(3)}-${rNumS(4)}`;

    const email =
      rString(rNum(), false) + '@' + rString(rNum(), false) + '.com';

    document.getElementsByTagName('input')[6].value =
      rString(10) + rString(rNum(5)) + ', LLC'; // llc name
    document.getElementsByTagName('input')[7].value = '1'; // num employees
    document.getElementsByTagName('select')[4].value =
      document.getElementsByTagName('select')[4].options[3].value; // title
    document.getElementsByTagName('input')[16].value = 'Owner'; // title
    document.getElementsByTagName('input')[17].value =
      rString(5, false) + rString(rNum(5)); // first
    document.getElementsByTagName('input')[18].value =
      rString(5, false) + rString(rNum(5)); // middle
    document.getElementsByTagName('input')[19].value =
      rString(5, false) + rString(rNum(5)); // last
    // ssn
    document.getElementsByTagName('input')[20].value = ssl;
    document.getElementsByTagName('input')[21].value = ssl;
    // address
    document.getElementsByTagName('input')[22].value =
      `${rNumS(rNum(5))} ` + rString(10) + rString(rNum(10)); // address 1
    document.getElementsByTagName('input')[23].value =
      rString(8) + rString(rNum(8)); // city
    document.getElementsByTagName('input')[24].value = state; // state
    document.getElementsByTagName('input')[25].value = rNumS(5); // zip

    document.getElementsByTagName('select')[6].value =
      document.getElementsByTagName('select')[6].options[1].value; // reason for applying
    document.getElementsByTagName('select')[7].value =
      document.getElementsByTagName('select')[7].options[12].value; // primary activity
    document.getElementsByTagName('input')[31].value = rString(25); // specific products or services

    document.getElementsByTagName('select')[11].value =
      document.getElementsByTagName('select')[11].options[rNum(12)].value; // business started month
    document.getElementsByTagName('select')[12].value =
      document.getElementsByTagName('select')[12].options[rNum(28)].value; // business started day
    document.getElementsByTagName('select')[13].value =
      document.getElementsByTagName('select')[13].options[2].value; // business started year
    document.getElementsByTagName('select')[26].value =
      document.getElementsByTagName('select')[26].options[rNum(12)].value; // month business year end
    document.getElementsByTagName('input')[47].value = phone;
    document.getElementsByTagName('input')[48].value = email;
    document.getElementsByTagName('input')[49].value = email;

    document.getElementsByTagName('input')[50].checked = true; // I agree

    // document.getElementsByTagName('input')[63].click(); // submit
    // window.history.go(-1) // go b/ack one -- not sure if this will work
  };
  setInterval(submitForm, 500);
};

```
