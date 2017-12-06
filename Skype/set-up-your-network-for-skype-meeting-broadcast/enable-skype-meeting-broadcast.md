---
title: "Skype 会議ブロードキャストを有効にする"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "Skype 会議ブロードキャスト使用、組織のユーザーには、有効にする必要があります。これを行うには、Windows PowerShell を使用する方法を理解する必要があります。Windows PowerShell がわからない場合に、この手順を行うには、 Microsoft パートナーの採用を検討してください。"
---

# Skype 会議ブロードキャストを有効にする

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](5299cce0-850e-42dc-b6ae-2d0ee775c4a9.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/5299cce0-850e-42dc-b6ae-2d0ee775c4a9)をクリックしてください。 
  
Skype 会議ブロードキャスト使用、組織のユーザーには、有効にする必要があります。これを行うには、Windows PowerShell を使用する方法を理解する必要があります。Windows PowerShell がわからない場合に、この手順を行うには、 [Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。
  
> [!CAUTION]
> Skype 会議ブロードキャスト既定でオフになってブロードキャスト会議のメディア コンテンツの配布は、ブロードキャストの視聴の桁をサポートする最高のスケールを達成するために Microsoft Azure のコンテンツ配信ネットワーク (CDN) を使用するためです。 CDN 通過チャンク メディア コンテンツが暗号化され、CDN キャッシュが一定期間のみ有効です。 また、Azure CDN コンポーネントがまだを満たしていない EU データ保護ディレクティブから生じる EU モデル句のすべての要素。この機能を有効にすると、この通知を確認します。 
  
## Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする

1. [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) でOffice 365 のグローバル管理者アカウントを使用してサインインします。
    
2. Office 365 管理センターで、[ **管理センター**] > [ **Skype for Business**] に移動します。
    
3. **Skype for Business 管理センター**で、[ **オンライン会議**] に移動 > **会議をブロードキャスト**して、 **Skype 会議メディアを有効にする**] を選びますします。
    
## PowerShell を使用して Skype 会議ブロードキャストを有効にする

1. Windows PowerShell のバージョン 3.0 以上を実行していることを確認します。
    
1. バージョン 3.0 以上を実行していることを確認するには、[ **スタート**] メニューで [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online 用の Windows PowerShell モジュールもインストールする必要があります。このモジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、Microsoft ダウンロード センターの「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。再起動を求めるメッセージが表示されたら、コンピューターを再起動します。
    
2. **[スタート] メニュー**で、 **Windows PowerShell**を選択します。
    
3. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
  Import-PSSession $O365Session
  ```

4. 以下のコマンドを実行して、現在の Skype 会議ブロードキャストの構成を確認します。
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

     _EnableBroadcastMeeting_ パラメーターが `False` に設定されていることを確認します。
    
     ![組織に対して Skype Meeting Broadcast を有効にするコマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. 以下のコマンドを実行して、組織の Skype 会議ブロードキャストを有効にします。
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

     `Get-CsBroadcastMeetingConfiguration`をもう一度実行して、設定が有効になっていることを確認することができます。
    
     ![組織に対して Skype Meeting Broadcast を有効にするコマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更後は、Skype 会議ブロードキャストのポータルに変更が反映されるまでに最長で 1 時間かかる場合があります。 
  
6. ユーザーは、ビジネスで他のユーザーとの会議をブロードキャストを今すぐ保持できます。作業を開始して、対象とする[Skype 会議ブロードキャストとは](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## ネットワークを構成して、外部の出席者に会議をブロードキャストする

ファイアウォールが構成されている場合に組織外 (フェデレーションされていない組織) の参加者とブロードキャストを開催する場合は、「[Skype 会議ブロードキャスト用にネットワークをセットアップする](set-up-your-network-for-skype-meeting-broadcast.md)」の手順に従ってネットワークを構成する必要があります。
  
ファイアウォールの構成に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。
  
この手順をスキップして、代わりに、フェデレーションを別の企業を追加、[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)を参照してください。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  
## 関連項目
<a name="MT_Footer"> </a>

#### 

[Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

