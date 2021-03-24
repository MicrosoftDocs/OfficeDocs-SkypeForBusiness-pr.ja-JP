---
title: 管理者が個々のユーザーに対して Skype for Business の設定を構成する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: '電話会議とビデオ会議、通話や会議の記録など、個々のユーザーの Skype for Business 設定を変更する方法について説明します。 '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093391"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理者: 個別のユーザーの Skype for Business の設定を構成する

> [!IMPORTANT]
> Microsoft Teams 管理センターは、Skype for Business 管理センター (レガシ ポータル) に置き換えました。 Skype for Business を管理するためのすべての設定が Teams 管理センターに表示されます。 Teams 管理センターで Skype for Business [AD](/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。 詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。

この記事では、管理者が少人数のユーザーに対して Skype for Business を構成する方法について説明します。 これらの手順を一括で実行するために、使用できる Windows PowerShellへのリンクが含まれています。
  
社外のユーザーとの通信を企業内のすべてのユーザーに許可 (またはブロック) するには、次を参照してください。
  
- ユーザーが[外部の Skype for Business](allow-users-to-contact-external-skype-for-business-users.md)ユーザーと連絡を取る : 組織で高度な Skype for Business 機能 (デスクトップの共有、オンラインのユーザーの検索など) を使用して、特定の信頼済み (フェデレーション) ビジネスのユーザーと通信することができます。 この記事では、特定のドメインとの通信をブロックする方法も説明します。
    
- [Skype for Business ユーザーが Skype の連絡先を追加します](let-skype-for-business-users-add-skype-contacts.md)。 組織で Skype for Business を使用して、無料アプリである Skype を使用するユーザーを検索して IM で入力することができます。
    
## <a name="configure-general-settings-for-one-user"></a>1 人のユーザーの全般設定を構成する
<a name="__toc325019204"> </a>

これらの手順を [実行するには、管理者権限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) が必要です。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**
  
1. 仕事用または学校用のアカウントでサインインします。
    
2. [**管理センター**]  >  [**Skype for Business**]を選択します。
    
3. [ **ユーザー**] を選びます。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 編集するユーザーを選択します。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. [全般 **] オプション** ページで、変更する機能の横にあるチェック ボックスをオンまたはオフにして、[保存] を選択 **します**。
    
|**オプション**|**詳細**|
|:-----|:-----|
|オーディオと HD ビデオ  <br/> |このユーザーが音声会議、音声会議、ビデオ会議を記録したり、会議のスケジュールを設定したり (なし) 許可したりしません。  <br/> |
|会話と会議を記録する  <br/> |このユーザーが記録できる情報を選択します。  <br/> このオプションは、Skype for Business Basic では使用できません。  <br/> |
|コンプライアンスの場合は、アーカイブされていない機能をオフにする  <br/> | 電子的に保存された情報を保存するために法的に要求される場合は、このオプションを選択します。 <br/>  このオプションを選択すると、Exchange 管理センターでインセット ホールドが設定[](/exchange/security-and-compliance/in-place-and-litigation-holds)されている場合にキャプチャされない機能がオフになります。 次の機能がオフになります。 <br/>  インスタント メッセージングを使用したファイルの転送 <br/>  OneNote の共有ページ <br/>  PowerPoint のコメント <br/> |
   
これらの設定を一括で構成するには、PowerShell を使用します。 「[コンピューターをセットアップする」を参照Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="block-external-communications"></a>外部通信をブロックする
<a name="__toc325019206"> </a>

Skype [for Business ユーザー](let-skype-for-business-users-add-skype-contacts.md) が会社のすべてのユーザーに Skype 連絡先を追加した後、次の手順を使用して、特定の個人の外部通信を選択的にブロックすることができます。
  
1. [ **ユーザー]** を選択し、設定を無効にするユーザーを選択し、[編集] を **選択** ![ します ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。
    
2. [外部 **通信] を** 選び、必要に応じてオプションをオフにします。
    
   - **外部の Skype for Business** ユーザー: フェデレーション ドメインの Skype for Business ユーザーとの通信を許可しない場合は、このボックスをオフにします。
    
   - **外部の Skype** ユーザー: FreeSkype アプリを使用しているユーザーと通信を許可しない場合は、このボックスをオフにします。
    
3. **[保存]** をクリックします。
    
これらの設定を一括で構成するには、PowerShell を使用します。 「[コンピューターをセットアップする」を参照Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>1 人のユーザーの電話会議設定を編集する
<a name="__toc314837483"> </a>

1. [ **ユーザー]** を選択し、電話会議の設定を編集するユーザーを選択し、[編集] を **選択** ![ します ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。
    
2. [ **電話会議] を選択し**、電話会議プロバイダーを選択し、要求された情報を入力または変更して、[保存] をクリック **します**。
    
|**電話会議の設定**|**説明**|
|:-----|:-----|
|**プロバイダー名** <br/> |一覧からプロバイダーを選択します。  <br/> |
|**有料電話番号** (必須) <br/> |サードパーティ ACP の場合、これらの電話番号は電話会議プロバイダーから受け取った電話番号です。 ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。 Skype for Business および Microsoft Teams の会議出席依頼に表示する数値の書式を設定します。  <br/> |
|**フリー ダイヤル番号** <br/> |サードパーティ ACP の場合、これらの電話番号は電話会議プロバイダーから受け取った電話番号です。 ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。 Skype for Business および Microsoft Teams の会議出席依頼に表示する数値の書式を設定します。  <br/> |
|**会議 ID と PIN** (必須) <br/> |このユーザーによってスケジュールされ、サードパーティの電話会議プロバイダーから提供された会議に参加するために使用される参加者 PIN または電話会議コード。 ユーザーが電話会議プロバイダーとして Microsoft を使用している場合、これは必要ありません。  <br/> |
   
これらの設定を一括で構成するには、PowerShell を使用します。 「[招待に含まれる電話番号を設定する Windows PowerShell」を参照](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[してください。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>関連項目 

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
