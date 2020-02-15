---
title: Skype for Business Online のレポートコマンドレットと REST web サービス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9046bb075fba832f0ba7c83697c96a285988fcf7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Skype for Business Online のレポートコマンドレットと REST web サービス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-09-05_

レポート機能と共に、Skype for Business Online は5つの Windows PowerShell コマンドレットへのアクセスを提供します。これらのレポートは、これらのレポートを生成するのに役立ちます。また、管理者がカスタマイズされたレポートデータを返すために使用することもできます。 また、Skype for Business Online には、開発者がカスタマイズされたレポート情報を取得するために使用できる REST ("対象の状態転送") も含まれています。

管理者が使用可能なレポートのコマンドレットは次のとおりです。

  - Get-CsActiveUserReport。アクティブユーザーの数 (つまり、少なくとも1つの会議またはピアツーピアの通信セッションに参加しているユーザー) の数に関する情報を提供します。

  - Get-csavconferencetimereport には、音声ビデオ会議で費やした時間 (分単位) に関する情報が表示されます。

  - Get-csconferencereport。ユーザーが参加した電話会議の数と種類に関する情報を提供します。

  - Get-csp2pavtimereport には、音声やビデオを含むピアツーピアセッションで費やした時間 (分単位) に関する情報が表示されます。

  - Get-csp2psessionreport。ユーザーが参加したピアツーピアセッションの数と種類に関する情報を提供します。

ほとんどの管理者は、Microsoft 365 管理センターで利用可能なレポートを使用します。これらのレポートは自動生成されるだけでなく、多くの場合、データはグラフィカルに表示されます。これらの値は、レポート作成のコマンドレット。 ただし、Windows PowerShell を使い慣れている管理者は、レポート作成コマンドレットを使用して、Lync Online レポートからすぐに利用できないデータを返すことができます。 たとえば、レポートコマンドレットは、セッション時間 (各セッションが持続する時間) に関する情報を返します。 各セッション期間は、Lync Online レポートを使用して使用することはできません。 同様に、毎日表示される Lync Online レポートには、過去14日間の情報のみが表示されます。 日単位の合計 (たとえば、4か月前の日付) を確認したい場合は、レポート作成コマンドレットを使用します。

また、管理者は[excel を使用して office 365 レポートデータを取得](http://msdn.microsoft.com/library/dn781442.aspx)することもできます。この記事では、Microsoft Excel の OData データ照会機能を使用してカスタムの office 365 レポートを作成する方法について説明します。 カスタムレポートを使用すると、Office 365 reporting service から返されるデータ (およびデータ量) を指定できます。 また、カスタムレポートを使用すると、データの並べ替えやグループ化の方法を指定したり、管理センターに表示されていない情報へのアクセスを提供したりすることもできます。

開発のバックグラウンドを備えた管理者は、REST web サービスを使用して、Skype for Business Online 管理センターに表示されていない情報を取得することができます。 REST サービスは SOAP サービスに似ていますが、各テクノロジでクライアントとサーバーの間で XML データを転送する方法が提供されています。 ただし、REST サービスには、SOAP サービスよりも少なくとも2つの利点があります。 1つの場合、REST は ATOM シンジケーション形式という標準形式を使用して XML データ転送を実行します。 対照的に、データを転送するときに、非標準形式を使用する SOAP。 また、REST は、GET と POST 以外の HTTP 動詞をブロックするネットワーク間でデータを転送することができます。

<div>

## <a name="see-also"></a>関連項目


[Lync Online レポート](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Office 365 Reporting Web サービス](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[Office 365 レポート Web サービスについての学習](http://msdn.microsoft.com/library/office/jj984321.aspx)  
[Exchange Online レポートのコマンドレット](http://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Excel を使用して Office 365 レポート データを取得する](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

