---
title: "Skype 会議ブロードキャスト用にネットワークをセットアップする"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Skype 会議ブロードキャスト用にネットワークをセットアップする

Skype 会議ブロードキャストを[Skype 会議ブロードキャストを有効にする](enable-skype-meeting-broadcast.md)にした後は、ネットワークを構成する必要があります。この手順は、組織外の参加者にウェビナーおよびその他のブロードキャストを開催する場合に実行します。
  
ファイアウォールの構成に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。
  
この手順をスキップし、代わりに別の組織をフェデレーションに追加してブロードキャストに招待できるようにする場合は、「[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)」の手順に従ってください。
  
## 手順 1: 許可したドメインをセットアップする

次の **いずれか** の方法を使用して、許可したドメインをセットアップします。
  
### 

 **方法 1: Office 365 管理センターを使用する**
  
1. **Office 365 管理センター**に移動し、左のナビゲーションで [ **設定**]、[ **サービスとアドイン**] をクリックしてから、 **Skype for Business** を選択します。
    
2. [ **External sharing (外部の共有)**] ページの [ **Domain exceptions (ドメインの例外)**] 下で、[ **All domains are blocked except (次以外のドメインをすべてブロック)**] を選択し、次のドメインを入力してカンマで区切ります。
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. [ **保存**] をクリックします。
    
### 

 **方法 2: Windows PowerShell を使用する**
  
- [ **スタート**] メニューで [ **Windows PowerShell**] を右クリックして、[ **管理者として実行**] をクリックします。[ **Windows PowerShell**] ウィンドウに次の行をそれぞれ入力して、Enter キーを押します。
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## 手順 2: Skype 会議ブロードキャストのドメインと URL、IP アドレスを追加する

セットアップ プロセスの 2 番目の手順では、最初に必要なドメインを追加して、Skype 会議ブロードキャストが機能するために必要な IP アドレスと URL を追加します。
  
- **必要なドメインのエンドポイントを追加します。**
    
    Skype 会議ブロードキャストを使用するには、クライアント コンピューターが次のエンドポイントにアクセスできるようにする必要があります。
    
|
|
|**行**|**用途**|**ソース | 資格情報**|**接続先**|**Office 365 向け ExpressRoute の BGP コミュニティ**|**CIDR アドレス**|**ポート**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**必須:** Skype for Business エンドポイント。 <br/> |「[Skype for Business Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)」を参照して、"必須" というラベルの付いた項目がすべてアクセス可能であることを確認します。  <br/> ||||
|2  <br/> |**必須:**[Skype 会議ブロードキャスト](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)の発表者と出席者  <br/> |クライアント コンピューター/ログオンしているユーザー  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|○  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|3  <br/> |**必須:**[Skype 会議ブロードキャスト](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)の発表者と出席者  <br/> |クライアント コンピューター/ログオンしているユーザー  <br/> |
```
aka.ms
amp.azure.net

```

|×  <br/> |該当なし  <br/> |TCP 443  <br/> |
|4  <br/> |**必須:**[Skype 会議ブロードキャスト](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)の発表者と出席者 (CDN を含む)  <br/> |クライアント コンピューター/ログオンしているユーザー  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|×  <br/> |該当なし  <br/> |TCP 443  <br/> |
   
- **必要な Skype for Business Online エンドポイントの URL と IP アドレスを追加します。どれが必要であるかは、**[ここ](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)で確認します。
    
## ハイブリッド展開と組織に Skype 会議ブロードキャストをセットアップする

Skype for Business Online 組織があり Lync Server 2010、Microsoft Lync Server 2013、および Skype for Business Server 2015 のオンプレミス展開があり、オンラインとオンプレミスの両方にユーザーがいる場合は、上記の手順に加えてその他の設定手順を完了して、オンプレミス組織が Skype for Business Online と通信でき、すべてのユーザーが Skype 会議ブロードキャストを作成して参加できるようにする必要があります。その要件については、「[Skype 会議ブロードキャストのオンプレミス展開を構成する](https://go.microsoft.com/fwlink/?LinkId=617070)」をご覧ください。
  
## 関連トピック

[Skype 会議ブロードキャストを有効にする](enable-skype-meeting-broadcast.md)
  
[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

