---
title: "個々 のユーザーのビジネス設定の管理者を構成する Skype"
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
description: "次のような Skype for Business 個々 のユーザーの設定を変更する方法について説明します。 音声とビデオ会議、通話の記録と会議します。 "
ms.openlocfilehash: 45b5e966a670dfc97d3edd27eae7811fad061638
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理者向け: ビジネス設定を個別のユーザー向けの Skype を構成します。

この記事では、管理者が少数のユーザー向けの Skype を構成する方法について説明します。一括で次の手順を行うには、Windows PowerShell コマンドレットを使用することができますへのリンク掲載されています。
  
許可する (またはブロック) を外部ユーザーと通信するために、ビジネスのすべての参加者を参照してください。
  
- [外部の Skype for Business ユーザーの連絡先にユーザーを許可する]](allow-users-to-contact-external-skype-for-business-users.md): 組織に使用することができます (デスクトップの共有、ユーザーが [オンラインなどの外観) のビジネス機能の Skype を高度な特定のユーザーと通信するために信頼できる (フェデレーション) のビジネスします。また、特定のドメインとの通信をブロックする方法についても説明します。
    
- [Skype の連絡先を追加する Skype for Business ユーザーができるように](let-skype-for-business-users-add-skype-contacts.md)します。組織がビジネスを検索し、Skype、無料のアプリを使用している IM ユーザーに Skype を使用することができます。
    
## <a name="configure-general-settings-for-one-user"></a>単一ユーザーの [全般] 設定を構成します。
<a name="__toc325019204"> </a>

次の手順を実行するのには、[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **管理センター**] を選びます > **Skype for Business**します。
    
3. **ユーザー**を選択します。
    
    ![Skype for Business 管理センター] では、ユーザーを選択します。](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 編集するユーザーを選択します。
    
5. 右のパネルで [**編集**] を選びます。
    
    ![[編集] アイコンを選択します。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. [**全般**] オプション ページで、選択や、変更する機能の横にあるチェック ボックスをオフにし、[**保存**] を選びます。
    
|**オプション**|**詳細情報**|
|:-----|:-----|
|音声とビデオの HD  <br/> |このレコードの音声会議に人、会議の音声とビデオを許可する、または任意 meeetings (なし) をスケジュールすることを許可しないです。  <br/> |
|会話および会議のレコーディング  <br/> |この人を記録することを許可する] を選びます。  <br/> このオプションは、Skype for Business の基本的なで利用可能なはできません。  <br/> |
|コンプライアンスのため、アーカイブされていない機能はオフにする  <br/> | 電子的に保存されている情報の保管を法律で要請されている場合は、このオプションを選択します。 <br/>  このオプションを選択するを[インプレース](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)で Exchange 管理センターの設定があるときにキャプチャされない機能をオフにします。次の機能をオフにします。<br/>  インスタント メッセージングを使用したファイルの転送 <br/>  OneNote の共有ページ <br/>  PowerPoint のコメント <br/> |
   
一括でこれらの設定を構成するには、PowerShell を使用します。[Skype for Business Online の管理ポリシー](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="block-external-communications"></a>外部通信をブロック
<a name="__toc325019206"> </a>

社内の全員の[Skype for Business ユーザーが Skype の連絡先を追加する](let-skype-for-business-users-add-skype-contacts.md)には、選択的に次の手順を使用して特定のユーザーに対して外部通信をブロックすることができます。
  
1. **ユーザー**を選択し、設定を無効にするには、ユーザーを選択し、[**編集**] を選んで![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)します。
    
2. **外部通信**] を選択し、[必要に応じてオプションをオフにします。
    
  - **外部の Skype for Business ユーザー**: ユーザーにフェデレーション ドメインのビジネス ユーザーの Skype との通信を行わない場合このボックスをオフにします。
    
  - **外部の Skype ユーザー**: freeSkype アプリを使用しているユーザーと通信できるようにするユーザーをたくない場合このボックスをオフにします。
    
3. {[**保存**] をクリックします。}
    
一括でこれらの設定を構成するには、PowerShell を使用します。[Skype for Business Online 組織外のユーザーとの組織との通信を管理する](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>単一ユーザーの電話会議の設定を編集します。
<a name="__toc314837483"> </a>

1. **ユーザー**を選び、[ユーザーが電話会議の設定を編集する、[**編集**] を選びます![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)します。
    
2. **電話会議**を選択電話会議プロバイダーを選び、または必要な情報を変更して入力し、[**保存**] をクリックします。
    
|**電話会議の設定**|**{Description}**|
|:-----|:-----|
|**プロバイダー名** <br/> |リストから、プロバイダーを選択します。  <br/> |
|**有料電話番号**(必須) <br/> |サードパーティ ACP には、これらの電話番号は、電話会議プロバイダーから受け取ったものです。ユーザーが電話会議プロバイダーとして Microsoft を使用している場合は、電話会議ブリッジに設定されている数値これらがされます。[数値の書式を設定して、ビジネスや Microsoft チーム会議出席依頼の Skype で表示されるようにしたいとします。  <br/> |
|**フリー ダイヤル番号** <br/> |サードパーティ ACP には、これらの電話番号は、電話会議プロバイダーから受け取ったものです。ユーザーが電話会議プロバイダーとして Microsoft を使用している場合は、電話会議ブリッジに設定されている数値これらがされます。[数値の書式を設定して、ビジネスや Microsoft チーム会議出席依頼の Skype で表示されるようにしたいとします。  <br/> |
|**電話会議 ID と PIN**(必須) <br/> |PIN の参加者または会議コード、このユーザーによってスケジュールされ、は、サードパーティ電話会議プロバイダーから提供を会議に参加するために使用します。ユーザーが電話会議プロバイダーとして Microsoft を使用している場合は、必要なこの、られません。  <br/> |
   
一括でこれらの設定を構成するには、PowerShell を使用します。[携帯電話への招待に含まれる数値の設定](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)を参照してください。


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>関連トピック 

[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[Skype Business および Microsoft チーム アドオン ライセンスを許可します。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
