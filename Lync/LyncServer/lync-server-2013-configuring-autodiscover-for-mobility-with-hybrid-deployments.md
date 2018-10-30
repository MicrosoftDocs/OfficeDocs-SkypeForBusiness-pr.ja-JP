---
title: 'Lync Server 2013: ハイブリッド展開での自動検出の構成によるモビリティ'
TOCTitle: ハイブリッド展開での自動検出の構成によるモビリティ
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48274104
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のハイブリッド展開での自動検出の構成によるモビリティ

 

_**トピックの最終更新日:** 2014-06-18_

ハイブリッド展開とは、Microsoft Lync Online クラウド サービスと内部設置型展開の両方を使用する構成です。この種類の構成では、自動検出サービスは、ユーザーの実際の場所を特定できなければなりません。つまり、自動検出は、内部設置型展開または Skype for Business Online の展開に関係なく、ユーザー アカウントおよびユーザー アカウントをホストするサーバーを探すのに役立ちます。

たとえば、ユーザー アカウントが Skype for Business Online のサーバーでホストされている場合、ユーザーを特定するには、*検出可能性* と呼ばれる次のプロセスが使用されます。

  - ユーザーは、内部設置型展開である **contoso.com** への接続を試行します。

  - この試行は、自動検出サーバーに関連付けられた DNS 名である lyncdiscover.contoso.com に送信されます。

  - 自動検出は、内部設置型展開の contoso.com にあるとされるレジストラー プールを参照し、Skype for Business Online でホストされるユーザーの実際のホーム サーバーに関する情報を受け取ります。その後、自動検出はユーザーに、**lync.com** オンライン自動検出サービスへの紹介を送信します。

  - ユーザーは lync.com オンライン自動検出サービスへの接続を試行し、ユーザーのアカウントおよびユーザーのホーム サーバーが特定されます。

ユーザー ホーム サーバーがある場所でモバイル クライアントが展開を検出できるようにするには、新しい URL (uniform resource locator) で自動検出サービスを構成する必要があります。自動検出サービスを構成するには次の手順に従います。

## ハイブリッド展開のための自動検出の構成

1.  Get-CsHostingProvider を使用して属性 ProxyFQDN の値を取得します。

2.  Lync Server 管理シェルで、次のように入力します。
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    \[identity\] は、共有 SIP アドレス スペースのドメイン名で置き換えます。

## 関連項目

#### その他のリソース

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

