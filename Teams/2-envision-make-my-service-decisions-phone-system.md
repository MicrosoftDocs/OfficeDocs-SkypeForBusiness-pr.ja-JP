---
title: Make Phone System with Calling Plans service decisions - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Choose from calling plans and licensing, configure emergency locations and features like voicemail and caller ID, acquire or transfer phone numbers.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e382992f3170f16718eac8d2c6f0902dbaff3b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="make-my-service-decisions"></a>Make my service decisions

## <a name="calling-in-teams"></a>Teams での通話

With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN). Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls from Teams client applications, with advanced features that include voicemail and emergency calling (enhanced 911).

> [!NOTE]
> The latest Teams roadmap for identifying Teams Audio Conferencing features in scope for your deployment can be found at <https://aka.ms/skype2teamsroadmap>.

## <a name="phone-system-in-teams"></a>Phone System in Teams

For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.

To enable connectivity to the PSTN, your organization can use Microsoft as its telecommunications service provider. Eventually, you’ll also have the option to “bring your own” telecommunications service provider to enable connectivity to PSTN for Phone System.

> [!IMPORTANT]
> The ability to choose your own telecommunications service provider for Phone System will be available in the future. To learn more about the projected timeline, please review the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap).

## <a name="phone-system-with-calling-plans"></a>通話プランが設定された電話システム

To use Microsoft as your telecommunications service provider, you need to obtain Calling Plan licenses and assign them to your Phone System users.

There are two major types of calling plans:

-   Domestic calling plan

-   Domestic and international calling plan

Each type of calling plan allocates a certain number of call minutes per month to each user who has been assigned the license. When the call minutes allocation is exhausted, the user won’t be able to place outbound calls—except for emergency calls—until the next month’s billing cycle. If you want users to be able to continue to place outbound call even after they’ve exhausted their allocation of call minutes, or to let users who have a domestic calling plan place international calls, you can set up Communications Credits for your organization.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>通話プランの利用可否

Before you plan for the implementation of Calling Plans in Teams, verify that the Calling Plans service is available in your area by reviewing [Country and region availability for Audio Conferencing and Calling Plans](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Due to legal constraints, for Calling Plans to be available to multinational organizations, the contract for Office 365 subscriptions must be based in a country or region where the Calling Plans service is available, or where the Calling Plans service can be purchased.

After confirming that your organization can obtain the Calling Plans service, compile the list of user locations or offices where you’ll be implementing the Calling Plans service, based on the list of available countries and regions.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide which user locations or offices you’ll implement the Calling Plans service in.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Document the user locations or offices to be enabled for the Calling Plans service.</li></ul>|

> [!TIP]
> Below is an example of a Phone System with Calling Plans site enablement list.
>|オフィス   |場所 |Phone System service  |
>|---------|---------|---------|
>|One Epping Road|オーストラリア|旧 PSTN サービス|
>|100 Cyberport Road|香港特別自治区|旧 PSTN サービス|
>|One Marina Boulevard|シンガポール|旧 PSTN サービス|
>|32 London Bridge Street|イギリス|通話プランが設定された電話システム|
>|39 quai du Président Roosevelt|フランス|通話プランが設定された電話システム|

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>電話番号と緊急対応の場所

With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dialing (DID) phone number and a corresponding validated emergency address. Review [Manage cloud voice telephone numbers](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers) to plan the phone number acquisition for your Calling Plans implementation.

When you’re configuring phone numbers for Calling Plans, you must assign an emergency address to each telephone number before you assign the number to a user. この指定は、緊急通話をサポートするために必要な操作です。 The emergency address must be validated to ensure that it’s in the correct format to be used by emergency response services.

> [!IMPORTANT]
> Emergency Services calling operates differently in the Calling Plans service than in traditional telephone services. It’s important that you understand these differences and communicate them to all users. See [Emergency Calling Terms and Conditions](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions) for more details.

In addition to supplying a validated emergency address, you can define emergency locations and associate them with the validated emergency address to give a more exact location within an address. 通常、緊急対応の場所はユーザーが勤務するビルの番号、階、棟、オフィス番号です。

To learn more about emergency locations in relation to Calling Plans, review the following articles:

-   [緊急対応の場所、住所、通話ルーティングの概要](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [緊急通話の利用条件](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the granularity of emergency location information to be collected for user locations or offices in scope for the Calling Plans implementation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Document the detailed emergency address and emergency locations for each user location or office in scope for the Calling Plans implementation.</li></ul>|

> [!TIP]
> You can use the following template to document the details of phone numbers and emergency location details.
>|ユーザー |Emergency location and address |Phone number |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 8901 |
>|Lidia Holloway |1065/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 89112 |
>|Louis Lahr |1023/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>ボイスメール

Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.

By default, Phone System voicemail works with Exchange Online; however it has a minimum supported Exchange on-premises version and deployment model to allow delivery of voicemail messages to user mailboxes in the on-premises Exchange deployment.

電話システムのボイスメールはボイスメールの議事録作成機能を備えています。この機能は組織のすべてのユーザーに対して既定で有効になっています。 Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization. If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking need to be enabled. See [Setting voicemail policies in your organization](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) for more details.

>[!NOTE]
> 電話システムのボイスメールには、SMTP を使用してメッセージを再送できるフォールバック メカニズムが実装されています。このメカニズムにより、サードパーティの電子メールシステムを利用するユーザーがボイスメール メッセージを受信することができます。 This mechanism doesn’t include guaranteed service uptime or other voicemail features, such as changing voicemail greeting.

For more information about voicemail in a Phone System implementation, see [Azure PBX voicemail support for Exchange Server](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether you’ll enable Phone System voicemail in your Calling Plans implementation.</li><li>If using Exchange on-premises and your existing deployment doesn’t meet your requirements to support Phone System voicemail, choose from the available options (upgrade and setup for Phone System voicemail support, migrate to Exchange Online, or leverage the fallback mechanism described earlier).</li><li>Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>If applicable, document the Exchange decision points to support Phone System voicemail.</li><li>If you’ll enable/disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</li></ul>|

> [!TIP]
> Phone System voicemail details for the Phone System with Calling Plans implementation can be documented as the following.
>|ユーザー |Exchange mailbox |Enable voicemail? |Voicemail transcription |Voicemail transcription profanity masking |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |オンライン      |はい |有効 |有効 |
>|Lidia Holloway   |オンライン      |はい |有効 |無効 |
>|Louis Lahr       |オンプレミス |はい |有効 |有効 |
>|Marcel Beauchamp |オンプレミス |はい |無効 |該当なし |
>|Rachelle Cormier |オンライン      |はい |無効 |該当なし |
>|Isabell Potvin   |オンプレミス |はい |無効 |該当なし |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>発信者番号

既定で、すべての通話の発信で発信に割り当てられた電話番号が発信者番号として使用されます。 通話の受信者は即座にその発信者を識別して通話を受け入れるか拒否するか決めることができます。 In some cases, there are legitimate business requirements to mask the Caller ID to protect the identity of callers by using the office main line number—this is typically a service number serviced by the Auto Attendant configuration—as Caller ID, or to block Caller ID presentation altogether.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether Caller ID manipulation is required for your Calling Plans implementation.</li><li>If applicable, decide the types of Caller ID manipulation (mask with service number or anonymize) to be implemented.</li><li>If applicable, decide which users require Caller ID manipulation and the type of Caller ID manipulation to be assigned to each user.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Document the users to be assigned Caller ID manipulation and the type of Caller ID manipulation to assign.</li></ul>|

> [!TIP]
> The following is an example of Caller ID masking details documentation.
>|ユーザー  |発信における発信者番号のマスク処理の有効化  |発信者番号のマスク処理の種類  |ユーザーによる上書きの許可  | 受信における発信者番号のマスク処理の有効化  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|いいえ|該当なし|はい|いいえ|
>|Lidia Holloway|はい|サービス番号 (OrgAA、+44 20 7946 0000)|いいえ|あり|
>|Louis Lahr|いいえ|該当なし|はい|いいえ|
>|Marcel Beauchamp|はい|サービス番号 (OrgAA、TBA)|いいえ|はい|
>|Rachelle Cormier|はい|匿名化|はい|いいえ|
>|Isabell Potvin|はい|サービス番号 (OrgAA、TBA)|いいえ|あり|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licensing for cloud voice capabilities

Audio Conferencing and Phone System are features in Office 365. They can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.

Calling Plans is an add-on to the Phone System feature in Office 365, so you must have a Phone System licensed enabled to use Calling Plans.

To support for additional Audio Conferencing and Calling Plans use cases (international conference dial-out, external calling after Calling Plan minute allocations are exhausted, and so on), you can set up Communications Credits for your organization.

## <a name="licensing-for-calling-plans"></a>通話プランのライセンス

If your organization intends to use Microsoft as telecommunications service provider, you need to obtain Calling Plan add-ons appropriate to your users’ business requirements. Generally, not everybody in an organization needs to place international calls, so you can provision most users with domestic Calling Plan licenses.

There are two types of Calling Plan licenses:

-   国内通話プラン

-   国内/国際通話プラン

> [!NOTE]
> ある特定ユーザーの「国内」はそのユーザーに割り当てられた Office 365 の使用場所によって決まります。

通話プランの各タイプで、ユーザーが利用できる月ごとの国内または国際通話の通話時間 (分) が割り当てられます。 The Domestic Calling Plan costs less compared to the International and Domestic Calling Plan.

The flexibility of subscribing and assigning the most appropriate Calling Plan type for individual users’ business requirements helps your organization control the costs of its Calling Plans implementation.

Office 365 テナントの場合、通話時間 (分) は国や地域別と通話プランの種類ごとに累積されます。 テナントに割り当てられた月ごとの通話時間の限度に達すると、その月の残りの期間、通話プラン サービス (緊急通話を除く) が停止されます。 The Calling Plans service will resume automatically on the first day of the next calendar month.

You can set up Communications Credits for your organizations to enable users to make outbound calls after the allocation of calling minutes is exhausted without having to wait until the next month billing cycle. Additionally, Communications Credits give users assigned the Domestic Calling Plan the ability to make international calls, which are then charged by using a “pay-per-minute” model.

To learn more about Phone System and Calling Plans, review the following articles:

-   [電話システム](https://products.office.com/skype-for-business/phone-system)

-   [通話プラン](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</li><li>Decide which users require a Domestic Calling Plan license and which require a Domestic and International Calling Plan license.</li><li>Decide whether you’ll need Communications Credits for your Calling Plans implementation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Document the division, department, office, or user groups you’ll assign a Phone System license with Domestic Calling Plan or Domestic and International Calling Plan.</li></ul>|

> [!TIP]
> You can use the following example to document the license assignment for Phone System with Calling Plans users.
>|ユーザー |オフィス |Office 365 ライセンス |Calling Plan |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Office 365 E5 |国内/国際通話プラン |
>|Lidia Holloway |32 London Bridge Street |Office 365 E5 |国内通話プラン |
>|Louis Lahr |32 London Bridge Street |Office 365 E5 |国内通話プラン |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, Phone System add-on |国内通話プラン |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |国内/国際通話プラン |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, Phone System add-on |国内通話プラン |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>コミュニケーション クレジット

Using Communications Credits, your users can dial out from an Audio Conferencing meeting to add someone else from anywhere in the world (outside of the originating country of the meeting organizer). You can set up Communications Credits for your organization to enable users to make outbound calls after they’ve exhausted their allocation of calling minutes, without having to wait until the next month’s billing cycle. Additionally, Communications Credits give users assigned with the Domestic Calling Plan the ability to make international calls, which are then charged by using a “pay-per-minute” model.

通信クレジットを実装するには、最初に初回購入金額を決定します。 If your organization chooses to use auto-recharge, you’ll determine the optimal amount by measuring actual usage. Monitor your Communications Credits usage over time, and adjust your recharge amount as required.

For your Calling Plans implementation, you can control the use of Communications Credits on a per-user basis, which helps you ensure that you’ve assigned these credits in alignment with your business needs.

To learn more about Communications Credits, review [What are Communications Credits?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether you need Communications Credits for your Audio Conferencing or Calling Plans implementation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Document the division, department, office, or user groups you’ll enable Communications Credits for.</li><li>Document your Communications Credits plan for your Audio Conferencing or Calling Plans implementation.</li></ul>|

> [!TIP]
> You use the following example to document the Communications Credits assignment list for Calling Plans users.
>|ユーザー |オフィス |Calling Plan |コミュニケーション クレジット |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |国内/国際通話プラン |有効 |
>|Lidia Holloway |32 London Bridge Street |国内通話プラン |無効 |
>|ルイ Lahr |32 London Bridge Street |国内通話プラン |有効 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |国内通話プラン |無効 |
>|Rachelle Cormier |39 quai du Président Roosevelt |国内/国際通話プラン |有効 |
>|Isabell Potvin |39 quai du Président Roosevelt |国内通話プラン |無効 |

<br>
> [!TIP]
> 次の例のように番号を計画、通信のクレジットを文書化することができます。
>|         |         |
>|---------|---------|
>|初回購入金額|$ 1,000|
>|リチャージを実行する金額|$400|
>|自動リチャージする金額|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>クラウド音声電話番号を管理します。

電話番号の管理のまま、独自の通信サービスのプロバイダーのことで電話システムを実装する場合に。

オーディオ会議と予定の呼び出しの実装では、新しい電話番号を取得するか、既存の電話番号を (ポート) を転送することができます。

To let users dial phone numbers the way they’re accustomed to—such as omitting area codes for local calls, omitting country code for domestic calls, or even using short-digit dialing when performing conference dial-out or calling other users in the organization—you can configure a customized dial plan and assign it to users.

## <a name="acquire-new-telephone-numbers"></a>Acquire new telephone numbers

The two types of telephone numbers in Microsoft cloud voice solutions are:

-   Subscriber (user) numbers, which can be assigned to users in your organization.

-   Service numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.

For more information about the types of telephone numbers, see [Different kinds of phone numbers used for Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

The total count of telephone numbers that you can obtain depend on the type of telephone number and the number of licenses you’ve bought and assigned to your users.

For more information about the total count of telephone numbers that you can obtain, see [How many phone numbers can you get?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|意思決定ポイント|<ul><li>ユーザーの場所やオフィスがマイクロソフトから新しい電話番号を取得する場所を決定します。</li><li>Microsoft から取得する電話番号の種類を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Document the user locations or offices where new telephone numbers will be acquired from Microsoft.</li><li>Document the type of telephone numbers to be acquired from Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfer existing telephone numbers

If your organization wants to transfer (or port) existing telephone numbers to Microsoft, you can do so by submitting a port order request to Microsoft.

You can transfer all your existing telephone numbers at once (full port), and—in some markets—you can transfer a subset of your existing telephone numbers (partial port). A partial port can be useful in cases where you just want to gradually move your users to Phone System with Calling Plans.

A single port order can only transfer the telephone numbers to a single telephone number type. If you need to transfer some of your telephone numbers as subscriber numbers and some as service numbers, we recommend that you first complete the transfer to Microsoft and then perform the conversion as soon as the numbers are in Microsoft’s control.

As an alternative (if partial port is supported), you can submit multiple port requests, one port request at a time. However, this alternative approach will prolong your contract with your existing telecommunications service provider.

Telephone number porting is a complex topic and requires thorough planning, coordination, and adequately managing your stakeholders’ expectations. To learn more, see the following articles:

-   [Transferring phone numbers to Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   電話番号の管理フォームのダウンロード

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|意思決定ポイント|<ul><li>ユーザーの所在地、またはオフィスの既存の電話番号をマイクロソフトに転送されますを決定します。</li><li>Decide the type of telephone numbers to be transferred to Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>文書化するには、ユーザーの所在地、またはオフィスの既存の電話番号をマイクロソフトに転送されます。</li><li>マイクロソフトに転送する電話番号の種類を文書化します。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システムの機能で、ダイヤル プランでは、変換する正規化ルールのセットを別の形式 (通常は E.164 形式) 承認と通話のルーティングの電話番号をダイヤルします。 オーディオ会議サービスでは、会議ダイヤルアウト用のシナリオ (たとえば、参加者を招待 PSTN とダイヤル バックでは、「電話」機能を使用して) でダイヤルされた電話番号を変換するために、電話システムで使用されるのと同じ機能を活用します。

In the Phone System feature of Office 365, there are two types of dial plans:

-   **Service dial plan:** This is the default dial plan that’s applied to users based on their Office 365 usage location, and it can’t be modified.

-   **Tenant dial plan:** This is a customizable dial plan within a tenant, which is further divided into two types:

    -   **Tenant-global dial plan:** The dial plan that applies to all users in the tenant.

    -   **Tenant-user dial plan:** The dial plan that applies only to specific users.

The effective dial plan assigned to users is the combination of the service dial plan (based on a user’s Office 365 usage location) and tenant dial plan (which can be either a tenant-global dial plan or tenant-user dial plan).

![Table shows three combinations of service and tenant dial plans.](media/audio_conferencing_image8.png "Table shows three combinations of service and tenant dial plans.")

> [!IMPORTANT]
> あります最大 25 の正規化ルールでは、各テナントのダイヤル プランです。したがってが使用されている正規化ルールと重複しないようにするのには重要なサービスの一部としてダイヤル プランです。

ダイヤル プランの詳細についてを参照してください[のダイヤル プランは何ですか?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|意思決定ポイント|<ul><li>組織にカスタマイズされたダイヤル プランが (ビジネス要件、導入要件、およびなど) が必要かどうかを決定します。</li><li>該当する場合、テナントのダイヤル プランのスコープを決定 (テナント グローバルまたはテナントのユーザー) カスタマイズしたダイヤル プランのお客様の要件をサポートします。</li><li>該当する場合は、クラウドのボイス実装のスコープ内のユーザーの所在地、またはオフィスをサポートするために作成するテナントのダイヤル プランを決定します。</li><li>該当する場合、カスタマイズされたダイヤル プランとテナントのダイヤル プランの各ユーザーに割り当てられるユーザーが必要なを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>クラウド ボイスの実装の一部として構成するには、カスタマイズされたダイヤル プランと関連付けられている正規化ルールを文書化します。</li><li>カスタマイズされたダイヤル プランとユーザーごとに割り当てられるテナントのダイヤル プランに割り当てられるユーザーを文書化します。</li></ul>|

> [!TIP]
> プロジェクトに適用可能な場合は、テナントのダイヤル プランの設定を文書化するのには次のテンプレートを使用できます。
>|テナント ダイヤル プランの名前<br>_説明_  |正規化ルールの名前<br>_説明_  |パターン<br>変換<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde、NSW、AU ダイヤル プラン_|**AU-NSW-NorthRyde-OER-Internal**<br>_One Epping Road オフィスの内部番号 (x7000 - x7999)、North Ryde、NSW、オーストラリア_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_NSW、オーストラリアの市内番号の正規化_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_オーストラリアの無料電話番号の正規化_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_オーストラリアのサービス番号の正規化_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_OMB Singapore、SG ダイヤル プラン_|**SG-OMB-Internal**<br>_行政管理予算局のオフィス、シンガポールの内部番号 (x8000-経費"x 8999)_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_シンガポールの無料電話番号の正規化_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_シンガポールのサービス番号の正規化_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux、フランスのダイヤル プラン_|**FR-39qdPR-Internal**<br>_39 quai du Président ルーズベルトのオフィス、Issy の内部番号 ("x-7999 x7000-経費)-ゴ-Moulineaux (フランス)_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_フランスの無料電話番号の正規化_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_フランスのサービス番号の正規化_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>False|

<br>
> [!TIP]
> 次のテンプレートの例を利用して、ダイヤル プランを文書化してプロジェクトをサポートすることができます。
>|ユーザー  |オフィス  |ダイヤル プランの種類  |ダイヤル プランの名前  |
>|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|テナント ダイヤル プラン|AU-NSW-NorthRyde-OER|
>|Alex Wilber|One Epping Road|テナント ダイヤル プラン|AU-NSW-NorthRyde-OER|
>|Ben Walters|One Epping Road|テナント ダイヤル プラン|AU-NSW-NorthRyde-OER|
>|Christie Cline|One Marina Boulevard|テナント ダイヤル プラン|SG-Singapore-OMB|
>|Debra Berger|One Marina Boulevard|テナント ダイヤル プラン|SG-Singapore-OMB|
>|Lee Gu|One Marina Boulevard|テナント ダイヤル プラン|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|サービス ダイヤル プラン|該当なし|
>|Lidia Holloway|32 London Bridge Street|サービス ダイヤル プラン|該当なし|
>|ルイ Lahr|32 London Bridge Street|サービス ダイヤル プラン|該当なし|
>|Marcel Beauchamp|39 quai du Président Roosevelt|テナント ダイヤル プラン|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|テナント ダイヤル プラン|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|テナント ダイヤル プラン|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>ドキュメント サービスに関する意思決定 

この資料の前のセクションからの情報を使用して、決定事項をサービスします。 一般に、このドキュメントは次の主要なセクションに含まれます。

-   通話プランが設定された電話システムのサイト有効化リスト

-   通話プランが設定された電話システムのユーザーへのライセンスの割り当て

-   通信クレジットの計画番号

-   電話番号の取得、電話番号、緊急対応の場所に関する詳細

-   ボイスメール設定の詳細

-   会議ブリッジの設定の割り当て

-   発信者番号のマスク処理の設定の詳細

-   テナント ダイヤル プラン

-   ダイヤル プランの割り当て

<!--ENDOFSECTION-->