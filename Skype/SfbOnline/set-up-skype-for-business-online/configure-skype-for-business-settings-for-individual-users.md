---
title: 管理者が個々のユーザー向けに Skype for Business の設定を構成する
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
description: 'Skype for Business の設定を変更する方法について説明します。たとえば、音声会議やビデオ会議、通話と会議の記録などがあります。 '
ms.openlocfilehash: cf54637bda51a7994121035b3db1585213c56c00
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753422"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理者: 個別のユーザーの Skype for Business の設定を構成する

> [!IMPORTANT]
> Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に代わるものです。 Skype for Business を管理するためのすべての設定が Teams 管理センターになりました。 Teams 管理センターで Skype for Business の機能を管理するには、グローバル管理者または Skype for Business 管理者の [AZURE AD 管理者の役割](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) が割り当てられている必要があります。 詳細については、「 [Microsoft Teams 管理センターで Skype For business の設定を管理](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)する」を参照してください。

この記事では、管理者が Skype for Business を少数のユーザーに対して構成する方法について説明します。 これらの手順をまとめて実行するには、使用できる Windows PowerShell コマンドレットへのリンクが含まれています。
  
組織内のすべてのユーザーが外部ユーザーと通信できるようにする (またはブロックする) には、以下を参照してください。
  
- [ユーザーが外部の skype For business ユーザーに連絡できるよう](allow-users-to-contact-external-skype-for-business-users.md)にする: Skype for business の高度な機能 (デスクトップの共有、オンラインのユーザーの検索など) を使用して、特定の信頼できる (フェデレーションされた) ビジネスのユーザーと通信できるようにします。 この記事では、特定のドメインとの通信をブロックする方法についても説明します。
    
- [Skype For business ユーザーが skype の連絡先を追加できるように](let-skype-for-business-users-add-skype-contacts.md)します。 Skype for Business を使用して、無料のアプリである Skype を使用しているユーザーを検索したり、IM を送信したりすることができます。
    
## <a name="configure-general-settings-for-one-user"></a>1人のユーザーの全般設定を構成する
<a name="__toc325019204"> </a>

これらの手順を実行するには、 [管理者権限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) が必要です。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**
  
1. 職場または学校のアカウントを使用してサインインします。
    
2. [**管理センター**]  >  [**Skype for Business**]を選択します。
    
3. [ **ユーザー**] を選びます。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 編集するユーザーを選びます。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. [ **全般** ] オプションページで、変更する機能の横のチェックボックスをオンまたはオフにして、[ **保存**] を選択します。
    
|**オプション**|**詳細**|
|:-----|:-----|
|オーディオと HD ビデオ  <br/> |このユーザーが音声会議、音声会議、ビデオ会議を記録したり、会議のスケジュールを設定したりできないようにします (なし)。  <br/> |
|会話と会議を記録する  <br/> |このユーザーが記録できる内容を選びます。  <br/> このオプションは、Skype for Business Basic では使用できません。  <br/> |
|コンプライアンスのため、アーカイブされていない機能をオフにする  <br/> | 電子的に保存された情報を維持する必要がある場合は、このオプションを選択します。 <br/>  このオプションを選択すると、Exchange 管理センターで [インプレースホールド](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) が設定されているときにキャプチャされていない機能は無効になります。 次の機能がオフになります。 <br/>  インスタント メッセージングを使用したファイルの転送 <br/>  OneNote の共有ページ <br/>  PowerPoint のコメント <br/> |
   
これらの設定をまとめて構成するには、PowerShell を使用します。 「 [Windows PowerShell 用にコンピューターをセットアップする」を](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)参照してください。
  
## <a name="block-external-communications"></a>外部通信をブロックする
<a name="__toc325019206"> </a>

[Skype For business ユーザー](let-skype-for-business-users-add-skype-contacts.md)が会社のすべてのユーザーに skype 連絡先を追加できるようにすると、次の手順を使用して、特定のユーザーの外部通信を個別にブロックすることができます。
  
1. [ **ユーザー**] を選び、設定を無効にするユーザーを選択して、 **[編集] を選び** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) ます。
    
2. [ **外部通信**] を選択し、必要に応じてオプションをオフにします。
    
   - **外部の skype For business ユーザー**: フェデレーションドメインの Skype for business ユーザーとの通信を可能にしない場合は、このボックスをオフにします。
    
   - **外部の Skype ユーザー**: freeSkype アプリを使用しているユーザーとの通信を可能にしない場合は、このボックスをオフにします。
    
3. [**保存**] をクリックします。
    
これらの設定をまとめて構成するには、PowerShell を使用します。 「 [Windows PowerShell 用にコンピューターをセットアップする」を](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)参照してください。
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>1人のユーザーの電話会議の設定を編集する
<a name="__toc314837483"> </a>

1. [ **ユーザー**] を選び、電話会議の設定を編集するユーザーを選び、[編集 **] を選び** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) ます。
    
2. [ **電話会議**] を選び、電話会議プロバイダーを選んで、要求された情報を入力または変更し、[ **保存**] をクリックします。
    
|**電話会議の設定**|**説明**|
|:-----|:-----|
|**プロバイダー名** <br/> |リストからプロバイダーを選択します。  <br/> |
|**有料電話番号** (必須) <br/> |サードパーティ ACP の場合、これらの電話番号は、電話会議プロバイダーから受け取った電話番号です。 ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。 Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。  <br/> |
|**フリー ダイヤル番号** <br/> |サードパーティ ACP の場合、これらの電話番号は、電話会議プロバイダーから受け取った電話番号です。 ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。 Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。  <br/> |
|**会議 ID と PIN** (必須) <br/> |このユーザーによってスケジュールされ、サードパーティの電話会議プロバイダーから提供された会議に参加するために使用される、参加者の PIN (会議コード) です。 ユーザーが Microsoft を電話会議プロバイダーとして使用している場合は、この操作は必要ありません。  <br/> |
   
これらの設定をまとめて構成するには、PowerShell を使用します。 「[招待に含まれている電話番号を設定する](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)」を[参照してください。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>関連項目 

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
