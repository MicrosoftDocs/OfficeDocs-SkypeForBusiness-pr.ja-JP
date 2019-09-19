---
title: 通話プランの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- LIL_Placement
description: 'Office 365 通話プラン (PSTN 通話プラン) でのライセンスの購入とセットアップの方法、電話番号を取得する方法、緊急連絡先と電話番号をユーザーに追加して割り当てる方法、ユーザーに新しい電話番号を通知する方法について説明します。 '
ms.openlocfilehash: 9f01c73c8374a367beb03db0a14df5dada0c562d
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494707"
---
# <a name="set-up-calling-plans"></a>通話プランの設定

他の Skype for Business のユーザーとの通話は無料です。ただし、ユーザーが社外のスマートフォンに電話をかけることができるようにする場合は、Office 365 で国内通話プランまたは国際通話プランを取得します。 ビジネス用の設定は簡単です。 

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>手順 1: お客様の国/地域で通話プランが使用できるかどうかを確認する
[電話会議および通話プランが利用可能な国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) で、お住まいの国と地域を選択し、電話会議、通話プラン、電話システム、有料または無料電話番号、通信クレジットについての情報を確認します。
  
## <a name="step-2-buy-and-assign-licenses"></a>手順 2: ライセンスを購入して割り当てる
1. Office 365 の電話システムがプランに含まれていない場合は、**電話システム** のアドオン ライセンスを購入する必要があります。 **電話システム** ライセンスを取得したら、[Office 365の通話プラン](calling-plans-for-office-365.md) を購入します。 ライセンスとプランの購入については、[Microsoft Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) を参照してください。 
    
    > [!TIP]
    > Office 365の **電話システム** ライセンスと通話プランは一緒になっているため、通話プラン購入のオプションを確認するには、最初に **電話システム** ライセンスを取得する必要があります。
  
2. まずライセンスを割り当て、組織内のユーザーに通話プランを割り当てます。 [Assign Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md) を参照してください。
    
## <a name="step-3-get-phone-numbers"></a>手順 3: 電話番号を取得する
新しいユーザー番号を取得する方法には次の 3 通りあります。

- **Skype for Business 管理センターを使用する。** 一部の国/地域では、Skype for Business 管理センターを使用してユーザーの電話番号を取得できます。詳細については [ユーザーの電話番号を取得する](/microsoftteams/getting-phone-numbers-for-your-users) を参照してください。
    
- **既存の番号を移行する。** 既存の番号を現在のサービス プロバイダーまたは電話会社から Office 365 に移行または転送します。 詳細については、[電話番号を Office 365 に移行する](transfer-phone-numbers-to-office-365.md) または [組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。  
  
- **新しい番号には申請書を使用します。** 国または地域によっては Skype for Business 管理センターを使用して新しい電話番号を取得することが出来ない場合があります。または、特定の電話番号またはエリアコードが必要です。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。 

## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>手順 4: 組織の緊急連絡先の住所と場所を追加する
<a name="bkmk_add_addresses"> </a> 緊急連絡先の住所は電話番号に関連付けられている必要があります。この関連付けが行われるかどうかは国と地域によって異なります。 例えば米国では、電話番号をユーザーに割り当てるときに、緊急対応の住所を関連付ける必要があります。 英国では、Office 365 から電話番号を取得するか、現在のサービス プロバイダーから電話番号を移すときに、緊急対応の住所をその電話番号に関連付ける必要があります。 

**組織の緊急連絡先の住所を追加する**

**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)

Skype for Business 管理センターで、 **[音声]** > **[緊急連絡先]** > **[新しいアドレスの追加]** に移動します。 詳細については [組織の緊急連絡先の住所を追加、削除する](/skypefor business/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization) をご覧ください。

**組織の緊急連絡先の場所を追加する** 

**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)

Skype for Business 管理センターで、 **[Voice]** > **緊急連絡先** > **[新しいアドレスの追加]** に移動します。 詳細については [組織の緊急対応の場所を追加、変更、削除する](/skypefor business/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization) をご覧ください。

    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>手順 5: ユーザーに緊急連絡先の住所と電話番号を割り当てる
<a name="bkmk_add_addresses"> </a> Office 365 の通話プランを設定する場合は、各ユーザーに電話番号と緊急連絡先を割り当てる必要があります。 電話番号に関連付けるには、先に緊急連絡先の住所を作成する必要があります。 

**ユーザーの緊急連絡先の住所を追加する方法** 

**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)

Skype for Business 管理センターで、**[音声]** > **[音声ユーザー]** > **[緊急連絡先の場所]** > **[番号の割当て]** > **[場所の変更]** に移動します。 詳細については [ユーザーの緊急連絡先の住所の割り当てまたは変更](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user) をご覧ください。

   > [!NOTE]
   > 電話番号を割り当てるときに、緊急連絡先の住所を割り当てることもできます。

**ユーザーに電話番号を割り当てる方法**

**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)

Skype for Business 管理センターで、**[音声]** > **[音声ユーザー]** > **[番号の割当て]** > **[場所の変更]** に移動します。 詳細については [ユーザーの電話番号を割り当て、変更、または削除する](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) をご覧ください。

## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>手順 6: 新しい電話番号をユーザーに通知する
<a name="bkmk_add_addresses"> </a>

メールを送信するか、会社の適切な連絡方法を使用して、ユーザーに新しい電話番号を伝えることをお勧めします。 

次に、ユーザーの **Skype for Business** アプリに電話番号がどのように表示されるかを示します。
  
1. デスクトップで Skype for Business にサインインします。
    
2.  **Settings** > **Tools** > **Options** を選択します。 
    
     ![[ツール] メニューの [オプション] のスクリーンショット](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. [**電話**] を選択します。 
    
    ![スマートフォンのオプションを選択するスクリーンショット](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
**Microsoft Teams** では、ユーザーは左側のナビゲーションで [**通話**] をクリックすると、自分の電話番号を表示できます。電話番号はダイヤル パッドの上部に表示されます。

![左側のナビゲーションの [通話] を選択するスクリーンショット。](media/teams-phone-number.png)

## <a name="what-else-do-you-need-to-know"></a>その他の情報
<a name="bkmk_add_addresses"> </a>

- 緊急対応の住所は、行政上の住所、所在地住所、または現住所と呼ばれることがあります。緊急対応の住所は、組織の事業所の場所を示す所在地住所または行政上の住所のことです。
    
- 緊急対応の場所は検証されません。緊急対応の住所だけが検証されます。
    
- 緊急対応の住所の詳細については、「[緊急対応の場所、アドレス、通話ルーティングの概要](what-are-emergency-locations-addresses-and-call-routing.md)」をご覧ください。
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>電話番号の割り当てを自動化したい場合
<a name="bkmk_add_addresses"> </a>

Windows PowerShell を使うことができる場合は、次のコマンドレットを使用して、ユーザーへの電話番号の割り当てを自動化できます。 
  
- [Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/library/mt243818.aspx): Business Voice Directory から電話番号を取得します。
    
- [Set-CsOnlineVoiceUser](https://technet.microsoft.com/library/mt243817.aspx): 電話番号を設定します。
    
詳しくは、「[クイック リファレンス: Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://technet.microsoft.com/library/dn362776%28v=ocs.15%29.aspx)」ご覧ください。
  
   > [!NOTE]
   > さらに多くの電話番号を取得する必要がある場合は、 [ビジネス製品に関するサポート (管理者向けヘルプ) に問い合わせる](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) にお問い合わせください。


## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](transferring-phone-numbers-common-questions.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 