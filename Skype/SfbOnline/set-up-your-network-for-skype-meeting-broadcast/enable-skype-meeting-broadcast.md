---
title: "Skype 会議メディアを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: "組織内のユーザー] を使用する Skype 会議メディアを有効にする必要があります。これを行うには、Windows PowerShell を使用する方法を理解する必要があります。Windows PowerShell がわからない場合は、この手順を行うには Microsoft パートナーを雇うを検討してください。"
ms.openlocfilehash: 3748ca75efcaed479e27fe253c5b3a8399e381d6
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 会議メディアを有効にします。

組織内のユーザー] を使用する Skype 会議メディアを有効にする必要があります。これを行うには、Windows PowerShell を使用する方法を理解する必要があります。Windows PowerShell がわからない場合は、この手順を行うには[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。
  
> [!CAUTION]
> Skype 会議メディア既定でオフになってブロードキャスト会議のメディア コンテンツの配布は、ブロードキャストの視聴の桁をサポートする最高のスケールを達成するために Microsoft Azure のコンテンツ配信ネットワーク (CDN) を使用するためです。CDN 通過チャンク メディア コンテンツが暗号化され、CDN キャッシュが一定期間のみ有効です。また、Azure CDN コンポーネントがまだを満たしていない EU データ保護ディレクティブから生じる EU モデル句のすべての要素。この機能を有効にすると、この通知を確認します。 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Business 管理センターの Skype を使用して、Skype 会議メディアを有効にします。

1. [Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)での自分の Office 365 グローバル管理者アカウントでサインインします。
    
2. Office 365 管理センターで**管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**で、[**オンライン会議**] に移動 > **会議をブロードキャスト**して、 **Skype 会議メディアを有効にする**] を選びますします。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell を使用して、Skype 会議メディアを有効にします。

1. Windows PowerShell の 3.0 以降のバージョンを実行することを確認します。
    
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
2. **[スタート] メニュー**で、 **Windows PowerShell**を選択します。
    
3. **Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. 実行して、現在の Skype 会議メディアの構成を確認します。
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    パラメーター _EnableBroadcastMeeting_に設定されていることを確認`False`します。
    
     ![Skype 会議メディアを有効にする組織コマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Skype 会議メディアの組織を実行して有効。 にします。
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    実行して、設定が有効になっていることを確認できる`Get-CsBroadcastMeetingConfiguration`もう一度します。
    
     ![Skype 会議メディアには、組織のコマンドレットが有効にします。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更を加えた後にかかることがあります 1 時間を Skype 会議メディア ポータルで有効にします。 
  
6. ユーザーは、ビジネスで他のユーザーとの会議をブロードキャストを今すぐ保持できます。作業を開始して、対象とする[Skype 会議メディアとは何ですか?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>外部の参加者との会議をブロードキャストするネットワークを構成します。

ファイアウォールがあり、ブロードキャスト (メンバーは、フェデレーション ビジネス) ビジネス以外の相手を保持する場合は、次の手順を使用して、ネットワークを構成する必要があります。: [Skype 会議メディア用にネットワークを設定](set-up-your-network-for-skype-meeting-broadcast.md)します。 
  
ファイアウォールの設定に経験豊富な場合は、この手順を行うには[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。
  
この手順をスキップして、代わりに、フェデレーションを別の企業を追加、[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)を参照してください。 
  
## <a name="related-topics"></a>関連トピック

[Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Skype for Business Online をセットアップします。](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

