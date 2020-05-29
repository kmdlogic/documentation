# How to register an API user for a customer

This document describes how a consumer can gain access to an API exposed on the Logic Marketplace.

## 1. Access request from the customer

In order to get access to Logic, the consumer needs to be able to access the [Logic Console](console). Today there are 2 different ways to achieve this - setting up a federation with Logic Identity and the consumers own identity store (company or municipal AD/AAD) or requesting to have a user created in the Logic Console user store. For both, the consumer needs to contact [support](mailto:logic-admin@kmd.dk) with the following information.

- Company name
- CVR number of the company
- Contact information:
  - Email address
  - Phone number

## 1. Create a Logic Subscription

When the consumer/partner is setup with access to the console the consumer will now have to setup a Logic subscription through the [Logic Console](console)
  
1. Go to [Logic Console](console)
2. Choose `Subscriptions` from the menu and then click on `Add Subscription`
3. Enter a `Subscription Name` of the partners name. Click on `Create`
4. Record the `Subscription Id`

You will now have a Logic Subscription. If you want to setup multiple subscriptions for better tracking, you can just go ahead and create more and you can switch between subscriptions by returning to the `Subscriptions` page and clicking `Activate` on the subscription you wish to manage.

## 1. Arrange for a Partner/Consumer Access and Client Credentials

To allow the consumer/partner to interact with [Logic Console](console) they will need to be registered for access. This can either be:

- By adding their Active Directory as a downstream provider for [Logic Console](console) (a good option for larger organisations)
- Adding users to the `Logic Console Users` AAD which is managed by the Logic team

If your API uses Logic Identity for authentication each partner might also require a `Client Credential` which will allow them to programmatically call your API.

Go to the [Logic Issues Dashboard](https://dev.azure.com/kmddk/KMDLoGIC/_dashboards/dashboard/02f46530-28bb-4962-bc2a-a12eabfe383e) and use the `New Work Item` widget to create your request.

Please include:

- The details of either:
  - The Active Directory of the partner to link
  - The Full Names and Email Addresses of the partners developers/users to be added to the `Logic Users` AAD
- A request for one or more Client Credentials including:
  - The Subscription ID of the partner that the credentials are to be linked to
  - The environments the partner needs access to (e.g. Momentum Demo, Momentum Production)

> NOTE: You will need to wait for at least the Client Credentials to be created before you can proceed.

Record the `User Name` and `Password` of any Logic Users registered on behalf of the partner.

## 1. Record the details of the Client Credentials

While the partners Logic Subscription is active in [Logic Console](console):

1. Choose the `Subscriptions` -> `Client Credentials` menu item
2. Expand the details panel for each client credential registered. Record the `client_id`, `client_secret` and `scope`.

## 1. Request Access to API and get an API Key

While the partners Logic Subscription is active in [Logic Console](console):

1. Choose the `Gateway` -> `Products` menu item
2. Find and choose the desired product for the environment(s) the partner has access to; e.g. `KMD Studica (Demo)`.
3. Go to the `Keys` tab and choose `Create Key`
4. Enter the partners name as the `API Key Name`. Choose the `Client Credential` from the drop-down which was created for you. Enter the details of the primary user. Click on `Submit`
5. Record the `Primary Key` from the `My Keys` list

## 1. Add the Partner to their Subscription

While the partners Logic Subscription is active in [Logic Console](console):

1. Choose the `Subscriptions` -> `Users` menu item
2. Choose `Invite User`, add each developer/user and give them a role of `Owner`
   1. For those with an integrated Active Directory, use their work email address
   2. For Logic Users, use the `User Name` given to you as their email address

## 1. Send information back to the customer

After above steps are complete you may send the information gathered to the partner, including:

- Logic User `Username` and temporary `Password` (if applicable)
- Logic `Subscription ID`
- Their client credentials `Client Id`, `Client Secret` and `Scope`
- Their `API Key`
- A link to the Logic Console <https://console.kmdlogic.io>

[console]:(https://console.kmdlogic.io)
