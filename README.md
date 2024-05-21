# Mocean monday.com SMS Automation User Documentation

## Looking for other documentation ?
- [MoceanAPI - SMS Broadcast Documentation](https://github.com/MoceanAPI/monday-dashboard)
- [MoceanAPI - Send SMS Documentation](https://github.com/MoceanAPI/monday-item/)
- [MoceanAPI - Omnichannel Messaging](https://github.com/MoceanAPI/monday-omnichannel)
- [MoceanAPI - SMS Automation Documentation](https://github.com/MoceanAPI/monday-automation/) (Current)
- [SMS Sender ID Country List](https://moceanapi.github.io/monday/)

## Contents
- [Features](#features)
- [Installation](#installation)
- [Non-Supported Trigger Methods](#non-supported-trigger-methods)
- [Notifications and Updates in monday.com](#notifications-and-updates-in-mondaycom)
- [Custom Date Time format](#custom-date-time-format)
- [Country Setting](#country-setting)
- [Voice Call](#voice-call)
    - [Virtual Number](#virtual_number) 
    - [Voice Recording](#voice-recording)
        - [Upload voice recording to Dropbox](#upload-voice-recording-to-dropbox)
        - [Upload voice recording to Github](#upload-voice-recording-to-github)
- [Whitelist IP Address](#whitelist-ip-address)
- [Frequently Asked Questions (FAQ)](#faq)

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
Contact us [here](mailto:sales@moceanapi.com) to setup your account for voice call capability.

### Virtual Number
By default, the `Number` we use to call your recipient is: `63001` which may be identified as `Spam  number` when your recipient receive the call.
To avoid this and get better answering chance, we suggest you to buy a virtual number from us [here](https://moceanapi.github.io/monday-two-way/#buy-a-virtual-number)

After you've bought your virtual number, you can select the virtual number in your `automation recipe`

![image](https://user-images.githubusercontent.com/24620178/226274870-c6ffa97a-6db0-446b-85b1-be775199782f.png)

### Voice Recording
If you've decided to send a **Voice Recording** instead of a **Text To Speech**, we have automation recipe that supports this. You will need to input the `Recording Link`

For the `Recording Link` input, you will need to supply a `Direct Link` to  the recording like below.

![image](https://user-images.githubusercontent.com/24620178/226282397-4126e678-a1f1-4a66-9339-478e0640a458.png)

Below, we will show you steps for 2 platform (Dropbox, Github) which you can upload your voice recording for free.

#### Upload voice recording to Dropbox

1. Create an account in [Dropbox](https://dropbox.com)
2. Upload your audio file and copy the link to your audio file
![image](https://user-images.githubusercontent.com/24620178/226578247-ad06eaf2-6862-4bb5-b3ff-1473db3be5f2.png)

3. Copy the parameter highlighted above from the uploaded URL and add it to the end of dl.dropboxusercontent.com, as demonstrated in the highlighted section below. 
![image](https://user-images.githubusercontent.com/24620178/226579167-287309fe-c4a3-457e-9aba-5ae3988cae7a.png)

So the final URL you should paste in the **Recording Link** in your automation recipe is: https://dl.dropboxusercontent.com/s/mpx3yi0cbrgsxeq/welcome%20to%20moceanapi.mp3
![image](https://user-images.githubusercontent.com/24620178/226548308-c2e3a125-0474-402b-97aa-ca1442ddc564.png)

#### Upload voice recording to Github

**Important** Files uploaded to public repository are accessible by everyone. If you want to limit access, we suggest you to go with **Dropbox**

**Public Repository**
1. Sign up for an account in [Github](https://github.com/signup)
2. On your left navigation panel, click on [**New**](https://github.com/new) to create a new repository
3. Give your repository a name. Eg: **Audio Files**
4. Scroll to the bottom and click on **Create Repository**
5. Upload your audio file
![image](https://user-images.githubusercontent.com/24620178/226539637-43710efb-d98b-4ccc-ac4b-d2ee060ad9d3.png)
6. Click on **Commit Changes**
7. Click on the newly uploaded file
![image](https://user-images.githubusercontent.com/24620178/226539871-a5d3dc63-accc-48b5-a6ab-ffff722ef0fe.png)
8. Right click on **View Raw** and copy the link
9. Paste the link in **Recording Link** in your automation recipe 
![image](https://user-images.githubusercontent.com/24620178/226540088-efea09cb-f5ae-45be-9f54-90028ce482ef.png)

## Whitelist IP Address

For added security, you should whitelist `192.168.4.1` IP address in your [MoceanAPI Dashboard](https://dashboard.moceanapi.com)

To do so, follow these steps

1. Go to [MoceanAPI Dashboard](https://dashboard.moceanapi.com/user/apisetting)
2. Navigate to **API Account** 
3. Key in **`192.168.4.1`** into **Allow IP** field

![image](https://user-images.githubusercontent.com/24620178/200761674-1ccb6e6c-2d7b-499d-bef6-ee47a3e2a624.png)

## FAQ
1. **Can I get Test Credits ?**
- You can get 20 FREE credits. Please note that once you make a top-up, the free credits will be removed.

2. **What means by 20 credits, 1 credit = EUR 1?**
- No, during the trial period, 1 credit equals 1 SMS. So, with 20 credits, you can test 20 SMS.

3. **Can I request more trial credits?**
- Yes, of course! If you&#39;d like to test further, feel free to request from us.

4. **Can I send international messages?**
- Yes. We are an international SMS provider. You can send out SMS both locally and internationally.
The price for each country varies, do check out our pricing list here (link to
https://moceanapi.com/pricing)

5. **What is the maximum characters per SMS I can put into the message?**
- English messages can be up to 160 characters, while for Unicode text messages (including Arabic,
Chinese, etc.), the limit is 70 characters.

6. **Do you support long message content?**
- Yes, you can send long message content and your credit will be deducted based on the length of the message content.

7. **Is there a limit to how many numbers I can send at one time?**
- There is no limit on numbers to be sent in one go.

8. **What format does my phone number need to be in?**
- Mobile phone numbers need to be entered in international formatting with the country code and without spaces, plus signs or leading zeros. Example: Country code 60 for country Malaysia, 60123456789

9. **What is the character limit for the sender/sender ID?**
- The alpha sender ID can be a maximum of 11 characters, while the numeric sender can consist of up to 15 digits.

10. **I attempted to send messages to US numbers, but they failed to be delivered. Why?**
- Message content that is not registered will result in a failure. To comply with US regulations, it’s essential to buy a number and undergo a use case verification before you can send SMS to your customers.

11. **Can I utilize my personal mobile or landline number as the sender for SMS to the US?**
- No, it’s necessary to purchase a dedicated number, such as a Toll-Free Number, and complete the use case verification process.

12. **How do I go about obtaining or purchasing a Toll Free Number in the US/Canada?**
- Steps:
1) Complete the number registration form available [here](https://docs.google.com/document/d/1b-VJCcCGcNgHXgm2dmelWW6m0vsN6Kfg/edit) 
2) Proceed with the payment.
3) After your registration is accepted and approved, you’ll be able to send and receive SMS using your Toll Free Number.

13. **What is the expected timeframe for number approval?**
- Yes, it is possible. We would need a LoA (Letter of Agency) signed to allow us to take over the SMS part of the number.

14. **I am currently having a TFN / 10DLC from another provider. I want to use the same number in your platform. Is that possible?**
- Yes, it is possible. We would need a LoA (Letter of Agency) signed to allow us to take over the SMS part of the number.

15. **Why my SMS failed to deliver?**
- You may have set an invalid sender ID, alphanumeric sender ID must be less than 12 characters, and numeric sender ID must be less than 16 characters. Another common issue is you did not specify the correct phone number format including country code. Example: Country code 60 for country Malaysia, 60123456789

16. **I want to purchase SMS credits, how to top up my account?**
- Easy &amp; fast, just follow a few steps below:
1) Login to your account at [https://dashboard.moceanapi.com/login](https://dashboard.moceanapi.com/login) 
2) Go to Top Up page on left menu
3) Select Payment
4) Pay with credit card / PayPal
Your account will be credited instantly and enjoy texting!

17. **Why I cannot buy a Virtual Number?**
- This is due to your account is under trial mode or has insufficient balance. Please top up before proceeding with number purchase.

18. **Why I cannot get monday.com Notifications after receiving an SMS reply?**
- You will need to connect your Monday.com account with us. We have a video for you to follow along to connect your Monday.com account and MoceanAPI. Check it out [here](https://www.youtube.com/watch?v=P1DG6grBlQ0)

19. **Do I need a Virtual Number to send 1-Way SMS?**
- No, you don’t need a Virtual Number to send 1-Way SMS, unless you are sending SMS to recipients in the US &amp; Canada.

**Did not find what you're looking for ?**

Do raise a support ticket with our Support Team at [support@moceanapi.com](mailto:support@moceanapi.com).

## Feature Request / Get Help
Do raise a support ticket with our Support Team at [support@moceanapi.com](mailto:support@moceanapi.com).
