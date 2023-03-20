# Mocean monday.com SMS Automation User Documentation

## Looking for other documentation ?
- [MoceanAPI - SMS Broadcast Documentation](https://moceanapi.github.io/monday-dashboard/)
- [MoceanAPI - Send SMS Documentation](https://moceanapi.github.io/monday-item/)
- [MoceanAPI - Two Way SMS Documentation](https://moceanapi.github.io/monday-two-way/)
- [MoceanAPI - SMS Automation Documentation](https://moceanapi.github.io/monday-automation/)  (Current)
- [SMS Sender ID Country List](https://moceanapi.github.io/monday/)

## Contents
- [Features](#features)
- [Installation](#installation)
- [Non-Supported Trigger Methods](#non-supported-trigger-methods)
- [Notifications and Updates in monday.com](#notifications-and-updates-in-mondaycom)
- [Custom Date Time format](#custom-date-time-format)
- [Country Setting](#country-setting)
- [Voice Call](#voice-call)
- [Whitelist IP Address](#whitelist-ip-address)
- [Frequently Asked Questions](#faq)

## Features
- Automatically send SMS when new Item is created
- Automatically send SMS on specific date
- Automatically send SMS when the status value changed
- Automatically send SMS when the column value changed
- Automatically send Voice Call (Text to speech) when new Item is created
- Automatically send Voice Call (Text to speech) on specific date
- Automatically send Voice Call (Text to speech) when the status value changed
- Automatically send Voice Call (Text to speech) when the column value changed

## Installation

1. Select the board you would like to install MoceanAPI Automation

2. Click on `Integrate`

![image](https://user-images.githubusercontent.com/24620178/153557889-12aac289-64c2-4ddc-b265-e3838e9703c9.png)

3. Click on `Integrations Center` and Search for `Mocean` in the search bar and install `MoceanAPI - Automation`

![image](https://user-images.githubusercontent.com/24620178/153558065-f8f9f4bc-ad8f-45db-9f43-91dabfde2a96.png)

4. Choose the automation that fits your needs and click `Add to board`

![image](https://user-images.githubusercontent.com/24620178/153558167-20baab8b-1d81-4fb3-8961-f0d4198a60ca.png)

5. Enter your Mocean API Credentials and the sender

![image](https://user-images.githubusercontent.com/24620178/203029859-d9273a25-20c2-47b9-8724-7739d51bb407.png)

6. After you've successfully authenticated, you will be redirected back to `Monday.com` to customize your `Automation Recipe`

![image](https://user-images.githubusercontent.com/24620178/153558546-4ea76118-41c5-496e-a02a-89736fc285b6.png)

7. After customizing your `Automation Recipe`, click on `Add to board` at bottom right

8. When the automation is triggered, the SMS log will be displayed in the `MoceanAPI - Item App` if you installed.

![image](https://user-images.githubusercontent.com/24620178/153558811-685771d1-bc23-4ba7-bf78-4301173af29a.png)

## Non-Supported Trigger Methods
1. Sending SMS when an item is created
    - The `new item` created does not have a `phone` field value upon creation.
    - `Workaround` would be to set up an automation recipe: `When Column Changes, Send SMS to Phone from Your Business Name` and manually update the phone column after new item is created.
2. Sending to `subitems` is not supported at the moment

## Notifications and Updates in monday.com
If you'd like to disable receiving notifications and updates in monday.com whenever an automated SMS is triggered, you can configure it in the **Update API Credentials Page**

1. First navigate to `MoceanAPI - Send SMS app` or `MoceanAPI - SMS Broadcast app`.

![image](https://user-images.githubusercontent.com/24620178/223055251-72aa588b-eac3-4b85-9a1d-e792a55fb1d4.png)

2. Then click on the `Update API Credentials Link`. You can then configure whether you'd like to receive notifications in monday.com for every `automated` SMS sent

![image](https://user-images.githubusercontent.com/24620178/203029535-98bc5e6d-572e-4ed5-8f45-66d5a2796989.png)

## Custom Date Time format
Sometimes you may want to display a different format for your date time column in your SMS sent using Automation, you can do it by specifying your desired format in the **Update API Credentials Page**

### Date Formats
- `YYYY`: 4-digit year `'2019'`
- `YY`: 2-digit year `'19'`
- `MMMM`: Full-length month `'June'`
- `MMM`: 3 character month `'Jun'`
- `MM`: Month of the year, zero-padded `'06'`
- `M`: Month of the year `'6'`
- `DD`: Day of the month, zero-padded `'01'`
- `D`: Day of the month `'1'`
- `Do`: Day of the month with numeric ordinal contraction `'1st'`

### Time Format
- `HH`: hour of day from 0-24, zero-padded, `'14'`
- `H`: hour of day from 0-24, `'14'`
- `hh`: hour of day on 12-hour clock, zero-padded, `'02'`
- `h`: hour of the day on 12 hour clock, `'2'`
- `mm`: minute, zero-padded, `'04'`
- `m`: minute, `'4'`
- `ss`: second, zero-padded
- `s`: second
- `A`: `'AM'` or `'PM'`
- `a`: `'am'` or `'pm'`

### Example
Below is an example how you can combine both Date & Time format to create a customized date time format.
|Value|Result|
|---|---|
|  `ddd, YYYY MMM DD, h:mm A` | Wed, 2022 Aug 10, 9:32 AM  |
| `MMMM d, YYYY HH:mm`  |  August 3, 2022 09:32 |

## Country Setting
Sometimes your data might not include a country code for the phone number, you can specify the country setting and we will automatically convert the number to the equivalent of your chosen country code. 
For eg: the number `0123456789` will be converted to `60123456789` for the country `Malaysia (MY)`

![image](https://user-images.githubusercontent.com/24620178/220264383-5ccfeab6-0777-417e-a86c-9679a0c60a9d.png)

**Configure this setting if you only send to one country and the phone number doesn't have a prepended country code**

**We will always prioritize the country code we get from your monday.com item**

![image](https://user-images.githubusercontent.com/24620178/220265401-b54eb38e-e7cd-4531-94f6-07dc7c755b71.png)

## Voice Call
### Virtual Number
By default, the `Number` we use to call your recipient is: `63001` which may identify as `Spam  number` when your recipient receive the call.
To avoid this and get better answering chance, we suggest you to buy a virtual number from us [here](https://moceanapi.github.io/monday-two-way/#buy-a-virtual-number) 
After you've bought your virtual number, you can select the virtual number in your `automation recipe`

![image](https://user-images.githubusercontent.com/24620178/226274870-c6ffa97a-6db0-446b-85b1-be775199782f.png)

### Voice Recording
For the `Recording Link` input,
You will need to supply a `Direct Link` to  the recording like below.

![image](https://user-images.githubusercontent.com/24620178/226282397-4126e678-a1f1-4a66-9339-478e0640a458.png)

In this example, we will use [AnonFiles](https://anonfiles.com/) to help you get started quickly without registering for an account.

1. Visit [AnonFiles](https://anonfiles.com/)
2. Click on **Upload File**
3. Upload your recording
4. Open the link in your browser 

![image](https://user-images.githubusercontent.com/24620178/226294797-5206c2f8-f44b-471b-bb7a-5bf9b630fef4.png)

5. Right click on **Download (15.66 KB)**

![image](https://user-images.githubusercontent.com/24620178/226295342-b3f6b35e-3312-4bf7-9899-c56a7e3ae771.png)

6. Copy the link address
7. Paste copied link into your **Automation Recipe**

![image](https://user-images.githubusercontent.com/24620178/226295513-e8d73c68-368c-437f-b67d-3a69d4d9b527.png)

## Whitelist IP Address

For added security, you should whitelist `192.168.4.1` IP address in your [MoceanAPI Dashboard](https://dashboard.moceanapi.com)

To do so, follow these steps

1. Go to [MoceanAPI Dashboard](https://dashboard.moceanapi.com/user/apisetting)
2. Navigate to **API Account** 
3. Key in **`192.168.4.1`** into **Allow IP** field

![image](https://user-images.githubusercontent.com/24620178/200761674-1ccb6e6c-2d7b-499d-bef6-ee47a3e2a624.png)

## FAQ
1. Can I get Test Credits ?

You can get 20 FREE credits and credits are valid for 14 days. Subject to approval.

2. Can I send international messages?

Yes. We are an international SMS provider. You can send out SMS both locally and internationally based on our price list.

3. What is the maximum characters per SMS I can put into the message?

160 characters for a normal text message, 70 characters for a Unicode text message (Arabic, Chinese, and etc)

4. Is there a limit to how many numbers I can send at one time?

There is no limit on numbers to be sent in one go.

5. What format does my phone number need to be in?

Mobile phone numbers need to be 
ed in international formatting with the country code and without spaces, plus signs or leading zeros.

**Did not find what you're looking for ?**

Do raise a support ticket with our Support Team at [support@moceanapi.com](mailto:support@moceanapi.com).

## Feature Request / Get Help
Do raise a support ticket with our Support Team at [support@moceanapi.com](mailto:support@moceanapi.com).
