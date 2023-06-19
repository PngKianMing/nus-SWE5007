<template>
   <form>
        <div class="form-row">
            <label for="name">Name</label>
            <input type="text" id="name" name="name">
        </div>
        <div class="form-row">
            <label for="date-of-birth">Date of Birth</label>
            <input type="date" id="date-of-birth" name="date-of-birth" min="" max="maxDate">

        </div>
        <div class="form-row">
            <label for="country">Country</label>
          <ejs-dropdownlist id='countries' ref='countries' :query='Query1' :dataSource='countryData' :index='countryindex' :fields='countryfields' :change='onCountryChange' placeholder='Select a country'></ejs-dropdownlist>
        </div>
        <div class="form-row">
            <label for="state">State</label>
          <ejs-dropdownlist id='states' ref='states' :query='Query2' :dataSource='stateData' :index='stateindex' :fields='statefields' :enabled='stateenabled' :change='onStateChange' placeholder='Select a state'></ejs-dropdownlist>
        </div>

        <div class="form-row">
            <label for="school">School Name</label>
            <input type="text" id="school" name="school">
        </div>
        <div class="form-row">
            <label for="years-stem-learning"># Years of STEM Learning</label>
            <div class="form-row">
                <ejs-dropdownlist id='STEMYear' ref='STEMYear' :dataSource='STEMYearData' :index='STEMYearindex' :fields='STEMYearfields' placeholder='Select a year'></ejs-dropdownlist>
            </div>
        </div>
        <div class="form-row">
            <label for="team-name">Team Name</label>
            <input type="text" id="team-name" name="team-name">
        </div>
        <div class="form-row">
            <label for="competition-choice">Competition Choice</label>
            <div class="form-row">
                <ejs-dropdownlist id='CompetitionType' ref='CompetitionType' :dataSource='CompetitionTypeData' :index='CompetitionTypeindex' :fields='CompetitionTypefields' placeholder='Select a competition type'></ejs-dropdownlist>
            </div>
        </div>
        <div class="form-row">
            <label for="age-group">Age Group</label>
            <ejs-dropdownlist id='ageGroupType' ref='ageGroupType' :dataSource='ageGroupData' :index='ageGroupindex' :fields='ageGroupfields' placeholder='Select an age group'></ejs-dropdownlist>
        </div>
        <div class="form-row">
            <label for="phone">Handphone Number</label>
            <input type="tel" id="phone" name="phone">
        </div>
        <div class="form-row">
            <label for="registration-channel">Registration Channel</label>
            <div class="form-row">
                <ejs-dropdownlist id='registrationChannel' ref='registrationChannel' :dataSource='registrationChannelData' :index='registrationChannelindex' :fields='registrationChannelfields' placeholder='Select a registration Channel'></ejs-dropdownlist>
            </div>
        </div>
        <div class="form-row">
            <label for="name">Teacher's Name</label>
            <input type="text" id="name" name="name">
        </div>
        <div class="form-row">
            <label for="email">Teacher's Email</label>
            <input type="email" id="email" name="email">
        </div>
        
        <input type="submit" value="Submit" @click="alert">
        
    </form>
</template>
<style>
body {
    font-family: Arial, sans-serif;
    background-color: #f0bd9d;
    padding: 20px;
}
form {
    max-width: 500px;
    margin: 0 auto;
    background: linear-gradient(to bottom right, #fff);
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: left;
}
label {
    display: block;
    margin-bottom: 10px;
    font-weight: bold;
}
.form-row {
    margin-bottom: 20px;
}
.form-row label {
    display: block;
    margin-bottom: 5px;
}
.form-row input,
.form-row select {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    font-size: 14px;
}
input[type="submit"] {
    padding: 10px 20px;
    background: linear-gradient(to bottom right, #db4340, #ff6f00);
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
}

@import "../../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-vue-dropdowns/styles/material.css";
  #container .padding-top {
    padding-top: 35px;
}
</style>
<script>
   
import Vue from 'vue';
import { DropDownListPlugin } from "@syncfusion/ej2-vue-dropdowns";
Vue.use(DropDownListPlugin);
import { Query } from '@syncfusion/ej2-data';
import VueSwal from 'vue-swal'
Vue.use(VueSwal)

export default {
  data () {
    return {
      countryData: [
        { CountryName: 'Afghanistan', CountryId: '1' },
        { CountryName: 'Aland Islands', CountryId: '2' },
        { CountryName: 'Albania', CountryId: '3' },
        { CountryName: 'Algeria', CountryId: '4' },
        { CountryName: 'American Samoa', CountryId: '5' },
        { CountryName: 'Andorra', CountryId: '6' },
        { CountryName: 'Angola', CountryId: '7' },
        { CountryName: 'Anguilla', CountryId: '8' },
        { CountryName: 'Antarctica', CountryId: '9' },
        { CountryName: 'Antigua and Barbuda', CountryId: '10' },
        { CountryName: 'Argentina', CountryId: '11' },
        { CountryName: 'Armenia', CountryId: '12' },
        { CountryName: 'Aruba', CountryId: '13' },
        { CountryName: 'Australia', CountryId: '14' },
        { CountryName: 'Austria', CountryId: '15' },
        { CountryName: 'Azerbaijan', CountryId: '16' },
        { CountryName: 'Bahamas', CountryId: '17' },
        { CountryName: 'Bahrain', CountryId: '18' },
        { CountryName: 'Bangladesh', CountryId: '19' },
        { CountryName: 'Barbados', CountryId: '20' },
        { CountryName: 'Belarus', CountryId: '21' },
        { CountryName: 'Belgium', CountryId: '22' },
        { CountryName: 'Belize', CountryId: '23' },
        { CountryName: 'Benin', CountryId: '24' },
        { CountryName: 'Bermuda', CountryId: '25' },
        { CountryName: 'Bhutan', CountryId: '26' },
        { CountryName: 'Bolivia', CountryId: '27' },
        { CountryName: 'Bonaire Sint Eustatius and Saba', CountryId: '28' },
        { CountryName: 'Bosnia and Herzegovina', CountryId: '29' },
        { CountryName: 'Botswana', CountryId: '30' },
        { CountryName: 'Bouvet Island', CountryId: '31' },
        { CountryName: 'Brazil', CountryId: '32' },
        { CountryName: 'British Indian Ocean Territory', CountryId: '33' },
        { CountryName: 'Brunei Darussalam', CountryId: '34' },
        { CountryName: 'Bulgaria', CountryId: '35' },
        { CountryName: 'Burkina Faso', CountryId: '36' },
        { CountryName: 'Burundi', CountryId: '37' },
        { CountryName: 'Cambodia', CountryId: '38' },
        { CountryName: 'Cameroon', CountryId: '39' },
        { CountryName: 'Canada', CountryId: '40' },
        { CountryName: 'Cape Verde', CountryId: '41' },
        { CountryName: 'Cayman Islands', CountryId: '42' },
        { CountryName: 'Central African Republic', CountryId: '43' },
        { CountryName: 'Chad', CountryId: '44' },
        { CountryName: 'Chile', CountryId: '45' },
        { CountryName: 'China', CountryId: '46' },
        { CountryName: 'Christmas Island', CountryId: '47' },
        { CountryName: 'Cocos (Keeling) Islands', CountryId: '48' },
        { CountryName: 'Colombia', CountryId: '49' },
        { CountryName: 'Comoros', CountryId: '50' },
        { CountryName: 'Congo', CountryId: '51' },
        { CountryName: 'Democratic Republic of the Congo', CountryId: '52' },
        { CountryName: 'Cook Islands', CountryId: '53' },
        { CountryName: 'Costa Rica', CountryId: '54' },
        { CountryName: 'Cote D\'Ivoire', CountryId: '55' },
        { CountryName: 'Croatia', CountryId: '56' },
        { CountryName: 'Cuba', CountryId: '57' },
        { CountryName: 'Curacao', CountryId: '58' },
        { CountryName: 'Cyprus', CountryId: '59' },
        { CountryName: 'Czech Republic', CountryId: '60' },
        { CountryName: 'Denmark', CountryId: '61' },
        { CountryName: 'Djibouti', CountryId: '62' },
        { CountryName: 'Dominica', CountryId: '63' },
        { CountryName: 'Dominican Republic', CountryId: '64' },
        { CountryName: 'Ecuador', CountryId: '65' },
        { CountryName: 'Egypt', CountryId: '66' },
        { CountryName: 'El Salvador', CountryId: '67' },
        { CountryName: 'Equatorial Guinea', CountryId: '68' },
        { CountryName: 'Eritrea', CountryId: '69' },
        { CountryName: 'Estonia', CountryId: '70' },
        { CountryName: 'Ethiopia', CountryId: '71' },
        { CountryName: 'Falkland Islands (Malvinas)', CountryId: '72' },
        { CountryName: 'Faroe Islands', CountryId: '73' },
        { CountryName: 'Fiji', CountryId: '74' },
        { CountryName: 'Finland', CountryId: '75' },
        { CountryName: 'France', CountryId: '76' },
        { CountryName: 'French Guiana', CountryId: '77' },
        { CountryName: 'French Polynesia', CountryId: '78' },
        { CountryName: 'French Southern Territories', CountryId: '79' },
        { CountryName: 'Gabon', CountryId: '80' },
        { CountryName: 'Gambia', CountryId: '81' },
        { CountryName: 'Georgia', CountryId: '82' },
        { CountryName: 'Germany', CountryId: '83' },
        { CountryName: 'Ghana', CountryId: '84' },
        { CountryName: 'Gibraltar', CountryId: '85' },
        { CountryName: 'Greece', CountryId: '86' },
        { CountryName: 'Greenland', CountryId: '87' },
        { CountryName: 'Grenada', CountryId: '88' },
        { CountryName: 'Guadeloupe', CountryId: '89' },
        { CountryName: 'Guam', CountryId: '90' },
        { CountryName: 'Guatemala', CountryId: '91' },
        { CountryName: 'Guernsey', CountryId: '92' },
        { CountryName: 'Guinea', CountryId: '93' },
        { CountryName: 'Guinea-Bissau', CountryId: '94' },
        { CountryName: 'Guyana', CountryId: '95' },
        { CountryName: 'Haiti', CountryId: '96' },
        { CountryName: 'Heard Island and Mcdonald Islands', CountryId: '97' },
        { CountryName: 'Holy See (Vatican City State)', CountryId: '98' },
        { CountryName: 'Honduras', CountryId: '99' },
        { CountryName: 'Hong Kong', CountryId: '100' },
        { CountryName: 'Hungary', CountryId: '101' },
        { CountryName: 'Iceland', CountryId: '102' },
        { CountryName: 'India', CountryId: '103' },
        { CountryName: 'Indonesia', CountryId: '104' },
        { CountryName: 'Islamic Republic of Iran', CountryId: '105' },
        { CountryName: 'Iraq', CountryId: '106' },
        { CountryName: 'Ireland', CountryId: '107' },
        { CountryName: 'Isle of Man', CountryId: '108' },
        { CountryName: 'Israel', CountryId: '109' },
        { CountryName: 'Italy', CountryId: '110' },
        { CountryName: 'Jamaica', CountryId: '111' },
        { CountryName: 'Japan', CountryId: '112' },
        { CountryName: 'Jersey', CountryId: '113' },
        { CountryName: 'Jordan', CountryId: '114' },
        { CountryName: 'Kazakhstan', CountryId: '115' },
        { CountryName: 'Kenya', CountryId: '116' },
        { CountryName: 'Kiribati', CountryId: '117' },
        { CountryName: 'Democratic People\'s Republic of Korea', CountryId: '118' },
        { CountryName: 'Republic of Korea', CountryId: '119' },
        { CountryName: 'Kosovo', CountryId: '120' },
        { CountryName: 'Kuwait', CountryId: '121' },
        { CountryName: 'Kyrgyzstan', CountryId: '122' },
        { CountryName: 'Lao People\'s Democratic Republic', CountryId: '123' },
        { CountryName: 'Latvia', CountryId: '124' },
        { CountryName: 'Lebanon', CountryId: '125' },
        { CountryName: 'Lesotho', CountryId: '126' },
        { CountryName: 'Liberia', CountryId: '127' },
        { CountryName: 'Libyan Arab Jamahiriya', CountryId: '128' },
        { CountryName: 'Liechtenstein', CountryId: '129' },
        { CountryName: 'Lithuania', CountryId: '130' },
        { CountryName: 'Luxembourg', CountryId: '131' },
        { CountryName: 'Macao', CountryId: '132' },
        { CountryName: 'The Former Yugoslav Republic of Macedonia', CountryId: '133' },
        { CountryName: 'Madagascar', CountryId: '134' },
        { CountryName: 'Malawi', CountryId: '135' },
        { CountryName: 'Malaysia', CountryId: '137' },
        { CountryName: 'Maldives', CountryId: '137' },
        { CountryName: 'Mali', CountryId: '138' },
        { CountryName: 'Malta', CountryId: '139' },
        { CountryName: 'Marshall Islands', CountryId: '140' },
        { CountryName: 'Martinique', CountryId: '141' },
        { CountryName: 'Mauritania', CountryId: '142' },
        { CountryName: 'Mauritius', CountryId: '143' },
        { CountryName: 'Mayotte', CountryId: '144' },
        { CountryName: 'Mexico', CountryId: '145' },
        { CountryName: 'Federated States of Micronesia', CountryId: '146' },
        { CountryName: 'Republic of Moldova', CountryId: '147' },
        { CountryName: 'Monaco', CountryId: '148' },
        { CountryName: 'Mongolia', CountryId: '149' },
        { CountryName: 'Montenegro', CountryId: '150' },
        { CountryName: 'Montserrat', CountryId: '151' },
        { CountryName: 'Morocco', CountryId: '152' },
        { CountryName: 'Mozambique', CountryId: '153' },
        { CountryName: 'Myanmar', CountryId: '154' },
        { CountryName: 'Namibia', CountryId: '155' },
        { CountryName: 'Nauru', CountryId: '156' },
        { CountryName: 'Nepal', CountryId: '157' },
        { CountryName: 'Netherlands', CountryId: '158' },
        { CountryName: 'Netherlands Antilles', CountryId: '159' },
        { CountryName: 'New Caledonia', CountryId: '160' },
        { CountryName: 'New Zealand', CountryId: '161' },
        { CountryName: 'Nicaragua', CountryId: '162' },
        { CountryName: 'Niger', CountryId: '163' },
        { CountryName: 'Nigeria', CountryId: '164' },
        { CountryName: 'Niue', CountryId: '165' },
        { CountryName: 'Norfolk Island', CountryId: '166' },
        { CountryName: 'Northern Mariana Islands', CountryId: '167' },
        { CountryName: 'Norway', CountryId: '168' },
        { CountryName: 'Oman', CountryId: '169' },
        { CountryName: 'Pakistan', CountryId: '170' },
        { CountryName: 'Palau', CountryId: '171' },
        { CountryName: 'Palestinian Territory', CountryId: '172' },
        { CountryName: 'Panama', CountryId: '173' },
        { CountryName: 'Papua New Guinea', CountryId: '174' },
        { CountryName: 'Paraguay', CountryId: '175' },
        { CountryName: 'Peru', CountryId: '176' },
        { CountryName: 'Philippines', CountryId: '177' },
        { CountryName: 'Pitcairn', CountryId: '178' },
        { CountryName: 'Poland', CountryId: '179' },
        { CountryName: 'Portugal', CountryId: '180' },
        { CountryName: 'Puerto Rico', CountryId: '181' },
        { CountryName: 'Qatar', CountryId: '182' },
        { CountryName: 'Reunion', CountryId: '183' },
        { CountryName: 'Romania', CountryId: '184' },
        { CountryName: 'Russian Federation', CountryId: '185' },
        { CountryName: 'Rwanda', CountryId: '186' },
        { CountryName: 'Saint Barthelemy', CountryId: '187' },
        { CountryName: 'Saint Helena', CountryId: '188' },
        { CountryName: 'Saint Kitts and Nevis', CountryId: '189' },
        { CountryName: 'Saint Lucia', CountryId: '190' },
        { CountryName: 'Saint Martin', CountryId: '191' },
        { CountryName: 'Saint Pierre and Miquelon', CountryId: '192' },
        { CountryName: 'Saint Vincent and the Grenadines', CountryId: '193' },
        { CountryName: 'Samoa', CountryId: '194' },
        { CountryName: 'San Marino', CountryId: '195' },
        { CountryName: 'Sao Tome and Principe', CountryId: '196' },
        { CountryName: 'Saudi Arabia', CountryId: '197' },
        { CountryName: 'Senegal', CountryId: '198' },
        { CountryName: 'Serbia', CountryId: '199' },
        { CountryName: 'Serbia and Montenegro', CountryId: '200' },
        { CountryName: 'Seychelles', CountryId: '201' },
        { CountryName: 'Sierra Leone', CountryId: '202' },
        { CountryName: 'Singapore', CountryId: '203' },
        { CountryName: 'Sint Maarten', CountryId: '204' },
        { CountryName: 'Slovakia', CountryId: '205' },
        { CountryName: 'Slovenia', CountryId: '206' },
        { CountryName: 'Solomon Islands', CountryId: '207' },
        { CountryName: 'Somalia', CountryId: '208' },
        { CountryName: 'South Africa', CountryId: '209' },
        { CountryName: 'South Georgia and the South Sandwich Islands', CountryId: '210' },
        { CountryName: 'South Sudan', CountryId: '211' },
        { CountryName: 'Spain', CountryId: '212' },
        { CountryName: 'Sri Lanka', CountryId: '213' },
        { CountryName: 'Sudan', CountryId: '214' },
        { CountryName: 'Suriname', CountryId: '215' },
        { CountryName: 'Svalbard and Jan Mayen', CountryId: '216' },
        { CountryName: 'Swaziland', CountryId: '217' },
        { CountryName: 'Sweden', CountryId: '218' },
        { CountryName: 'Switzerland', CountryId: '219' },
        { CountryName: 'Syrian Arab Republic', CountryId: '220' },
        { CountryName: 'Taiwan,  Province of China', CountryId: '221' },
        { CountryName: 'Tajikistan', CountryId: '222' },
        { CountryName: 'United Republic of Tanzania', CountryId: '223' },
        { CountryName: 'Thailand', CountryId: '224' },
        { CountryName: 'Timor-Leste', CountryId: '225' },
        { CountryName: 'Togo', CountryId: '226' },
        { CountryName: 'Tokelau', CountryId: '227' },
        { CountryName: 'Tonga', CountryId: '228' },
        { CountryName: 'Trinidad and Tobago', CountryId: '229' },
        { CountryName: 'Tunisia', CountryId: '230' },
        { CountryName: 'Turkey', CountryId: '231' },
        { CountryName: 'Turkmenistan', CountryId: '232' },
        { CountryName: 'Turks and Caicos Islands', CountryId: '233' },
        { CountryName: 'Tuvalu', CountryId: '234' },
        { CountryName: 'Uganda', CountryId: '235' },
        { CountryName: 'Ukraine', CountryId: '236' },
        { CountryName: 'United Arab Emirates', CountryId: '237' },
        { CountryName: 'United Kingdom', CountryId: '238' },
        { CountryName: 'United States', CountryId: '239' },
        { CountryName: 'United States Minor Outlying Islands', CountryId: '240' },
        { CountryName: 'Uruguay', CountryId: '241' },
        { CountryName: 'Uzbekistan', CountryId: '242' },
        { CountryName: 'Vanuatu', CountryId: '243' },
        { CountryName: 'Venezuela', CountryId: '244' },
        { CountryName: 'Viet Nam', CountryId: '245' },
        { CountryName: 'British Virgin Islands', CountryId: '246' },
        { CountryName: 'Virgin Islands  U.s.', CountryId: '247' },
        { CountryName: 'Wallis and Futuna', CountryId: '248' },
        { CountryName: 'Western Sahara', CountryId: '249' },
        { CountryName: 'Yemen', CountryId: '250' },
        { CountryName: 'Zambia', CountryId: '251' },
        { CountryName: 'Zimbabwe', CountryId: '252' },

      ],
      stateData: [
        { StateName: 'Singapore', CountryId: '203', StateId: '2031' },
        { StateName: 'Johor', CountryId: '137', StateId: '1371' },
        { StateName: 'Kedah', CountryId: '137', StateId: '1372' },
        { StateName: 'Kelantan', CountryId: '137', StateId: '1373' },
        { StateName: 'Kuala Lumpur', CountryId: '137', StateId: '1374' },
        { StateName: 'Labuan', CountryId: '137', StateId: '1375' },
        { StateName: 'Melaka', CountryId: '137', StateId: '1376' },
        { StateName: 'Negeri Sembilan', CountryId: '137', StateId: '1377' },
        { StateName: 'Pahang', CountryId: '137', StateId: '1378' },
        { StateName: 'Penang', CountryId: '137', StateId: '1379' },
        { StateName: 'Perak', CountryId: '137', StateId: '13710' },
        { StateName: 'Perlis', CountryId: '137', StateId: '13711' },
        { StateName: 'Putrajaya', CountryId: '137', StateId: '13712' },
        { StateName: 'Sabah', CountryId: '137', StateId: '13713' },
        { StateName: 'Sarawak', CountryId: '137', StateId: '13714' },
        { StateName: 'Selangor', CountryId: '137', StateId: '13715' },
        { StateName: 'Terengganu', CountryId: '137', StateId: '13716' },
      ],
      STEMYearData: [
        { STEMYearName: '0', STEMYearId: '0'},
        { STEMYearName: '1', STEMYearId: '1'},
        { STEMYearName: '2', STEMYearId: '2'},
        { STEMYearName: '3', STEMYearId: '3'},
        { STEMYearName: '4', STEMYearId: '4'},
        { STEMYearName: '5', STEMYearId: '5'},
        { STEMYearName: '6', STEMYearId: '6'},
        { STEMYearName: '7', STEMYearId: '7'},
        ],
      CompetitionTypeData: [
        { CompetitionTypeName: 'Robotics', CompetitionTypeID: 'RB'},
        { CompetitionTypeName: 'Artificial Intelligence', CompetitionTypeID: 'AI'},
        { CompetitionTypeName: 'Programming', CompetitionTypeID: 'PG'},
      ],
      ageGroupData: [
        { ageGroupName: 'Primary School Learners (Age 7 - 12)', ageGroupNameID: 'g1'},
        { ageGroupName: 'Secondary School Learners (Age 13 - 16)', ageGroupNameID: 'g2'},
        { ageGroupName: 'Junior College Learners (Age 17 - 18)', ageGroupNameID: 'g3'},
        { ageGroupName: 'University Learners (Age 19 & Above)', ageGroupNameID: 'g4'},
      ],
      registrationChannelData: [
        { registrationChannelName: 'Social Media', registrationChannelID: 'Social Media'},
        { registrationChannelName: 'Whatsapp', registrationChannelID: 'Whatsapp'},
      ],
      countryfields : { value: 'CountryId', text: 'CountryName' },
      statefields : { value: 'StateId', text: 'StateName' },
      STEMYearfields : { value: 'STEMYearId', text: 'STEMYearName' },
      CompetitionTypefields : { value: 'CompetitionTypeId', text: 'CompetitionTypeName' },
      ageGroupfields : { value: 'ageGroupId', text: 'ageGroupName' },
      registrationChannelfields : { value: 'registrationChannelId', text: 'registrationChannelName' },
      countryindex : 202,
      stateindex : 0,
      stateenabled : false,
      Query1: null,
      Query2: null,
    }
  },
 
  methods: {
        onCountryChange: function(e) {
            this.Query2 = new Query().where('CountryId', 'equal', this.$refs.countries.ej2Instances.value);
            this.stateenabled = true;
        }, 
        alert() {
            this.$swal("Good job!", "You clicked the button!", "success");
        }
    },
}
</script>

