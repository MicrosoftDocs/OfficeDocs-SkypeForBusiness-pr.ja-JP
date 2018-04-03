---
title: 管理者の個々 のユーザー設定のビジネスの Skype の構成
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: '個々 のユーザーについては、ビジネスの Skype を次のように変更する方法について: オーディオおよびビデオ会議、通話の記録との会議。 '
ms.openlocfilehash: 8659434542696ccb37a0353cd491cc0d01f01e30
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理者: 個々 のユーザーについては、ビジネスの Skype を構成します。

この資料では、管理者がユーザーの数が少ないためにビジネスの Skype をどのように構成する方法について説明します。 一括でこれらの手順を行うには、Windows PowerShell コマンドレットを使用することができますへのリンク掲載されています。
  
許可 (またはブロック) 外部ユーザーと通信するためにお客様のビジネスのすべてのメンバーを参照してください。
  
- [ビジネス ユーザー向けの外部の Skype に連絡を許可する](allow-users-to-contact-external-skype-for-business-users.md): 組織が使用できるように Skype をビジネス機能 (デスクトップの共有、オンラインなどは、ユーザーのファイルの場所) の高度な特定のユーザーと通信するために信頼できるビジネス (連合)。 特定のドメインとの通信をブロックする方法についても説明します。
    
- [ビジネス ユーザー向けの Skype は、Skype 連絡先を追加](let-skype-for-business-users-add-skype-contacts.md)します。 組織のビジネスを検索するのには、Skype では、無料のアプリを使用する IM ユーザーの Skype を使用することができます。
    
## <a name="configure-general-settings-for-one-user"></a>1 人のユーザーの一般的な設定を構成します。
<a name="__toc325019204"> </a>

次の手順を実行する[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Choose **Admin centers** > **Skype for Business**.
    
3. [ **ユーザー**] を選びます。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 編集しユーザーを選択します。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. [**全般**オプション] ページで、選択または、変更する機能の横にチェック ボックスをオフにし、**保存**します。
    
|**オプション**|**詳細**|
|:-----|:-----|
|オーディオと HD ビデオ  <br/> |させるにはこのユーザーがレコードのオーディオ会議、オーディオおよびビデオ会議、または (なし)、meeetings のスケジュールを設定することができません。  <br/> |
|レコードの会話と会議  <br/> |このユーザーの許可を記録する」を選択します。  <br/> このオプションでは、ビジネスの基本の Skype で利用可能なできません。  <br/> |
|準拠するため非アーカイブ機能を無効にします。  <br/> | 電子的に保存されている情報を保持するために法的に必要な場合は、このオプションを選択します。 <br/>  このオプションを選択することは、[インプレース保持](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)Exchange 管理センターで設定がある場合にキャプチャされていない機能を無効にします。 次の機能をオフにします。 <br/>  インスタント メッセージングを使用したファイルの転送 <br/>  OneNote の共有ページ <br/>  PowerPoint のコメント <br/> |
   
一括でこれらの設定を構成するには、PowerShell を使用します。 [Skype のビジネスをオンラインで管理するポリシー](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="block-external-communications"></a>ブロック外部との連絡
<a name="__toc325019206"> </a>

すべてのユーザー、会社の[ビジネス ユーザー向けの Skype は、Skype 連絡先を追加](let-skype-for-business-users-add-skype-contacts.md)した後、次の手順を使用して特定の個人の外部との連絡を選択的にブロックできます。
  
1. **ユーザー**を選択し、ユーザー設定を無効にするを選択し、**編集**を選択し、![の編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。
    
2. **外部との連絡**を選択し、必要に応じてオプションをオフにし、します。
    
  - **ビジネス ユーザー向けの外部の Skype**: このボックスをオフにしない場合は、ユーザーがフェデレーション ドメイン内のビジネス ユーザーの Skype で通信できるようにします。
    
  - **外部 Skype ユーザー**: freeSkype アプリケーションを使用しているユーザーと通信できることをユーザーがしない場合はこのボックスをオフにします。
    
3. [ **保存**] をクリックします。
    
一括でこれらの設定を構成するには、PowerShell を使用します。 [外部のユーザーや組織のビジネスのオンラインの Skype での通信を管理する](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>1 人のユーザーのオーディオ会議設定を編集します。
<a name="__toc314837483"> </a>

1. **ユーザー**を選択して、電話会議の設定を編集するユーザーを選択、し、[**編集**] をクリックし、![を編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。
    
2. **オーディオ会議**を選択してオーディオ会議プロバイダーを選択して、または要求された情報を変更し、入力し、[**保存**] をクリックします。
    
|**電話会議の設定**|**説明**|
|:-----|:-----|
|**プロバイダー名** <br/> |リストから、プロバイダーを選択します。  <br/> |
|**有料電話番号** (必須) <br/> |サード ・ パーティ製 ACP では、これらの電話番号は、オーディオ会議プロバイダーから入手したものです。 場合は、ユーザーは、Microsoft を使用してオーディオ会議プロバイダーとしては、これらをオーディオ会議ブリッジで設定されている番号となります。 ビジネスおよびマイクロソフトのチームの会議出席依頼の Skype に表示する数値書式を設定します。  <br/> |
|**フリー ダイヤル番号** <br/> |サード ・ パーティ製 ACP では、これらの電話番号は、オーディオ会議プロバイダーから入手したものです。 場合は、ユーザーは、Microsoft を使用してオーディオ会議プロバイダーとしては、これらをオーディオ会議ブリッジで設定されている番号となります。 ビジネスおよびマイクロソフトのチームの会議出席依頼の Skype に表示する数値書式を設定します。  <br/> |
|**会議 ID と暗証番号 (pin)**(必須) <br/> |参加者暗証番号 (pin)、または会議コード、このユーザーが自動的にスケジュールし、サード ・ パーティ製のオーディオ会議プロバイダーから提供されているミーティングに参加するために使用します。 場合は、ユーザーは、Microsoft を使用してオーディオ会議プロバイダーとしては、必要な必要はありません。  <br/> |
   
一括でこれらの設定を構成するには、PowerShell を使用します。 「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)」をご覧ください。


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>関連トピック 

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 