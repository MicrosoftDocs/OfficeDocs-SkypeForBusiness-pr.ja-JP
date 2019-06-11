---
title: Skype for Business Online のレポートコマンドレットと REST web サービス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a140ed48ac662daea14d602f0830b2fbc4bf1c05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Skype for Business Online のレポートコマンドレットと REST web サービス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-09-05_

Skype for Business Online は、レポート機能と併用することで、これらのレポートを生成するのに役立つ5つの Windows PowerShell コマンドレットへのアクセスを提供します。また、カスタマイズされたレポートデータを返すために管理者が使用することもできます。 Skype for Business Online には、REST (対象指定) も含まれます。これは、開発者がカスタマイズしたレポート情報を取得するために使用できます。

管理者が利用できるレポートコマンドレットには、次のものがあります。

  - CsActiveUserReport を取得します。これは、アクティブなユーザー (つまり、Skype for Business Online にログインしていて、少なくとも1つの会議またはピアツーピア通信セッションに参加しているユーザー) の数に関する情報を提供します。

  - CsAVConferenceTimeReport は、音声/ビデオ会議で費やした時間 (分) に関する情報を提供します。

  - CsConferenceReport は、ユーザーが参加した会議の数と種類に関する情報を提供します。

  - CsP2PAVTimeReport は、オーディオやビデオが含まれているピアツーピアセッションでユーザーが費やした時間 (分) に関する情報を提供します。

  - Get-CsP2PSessionReport は、ユーザーが参加したピアツーピアセッションの数と種類に関する情報を提供します。

ほとんどの管理者は、Office 365 管理センターで利用可能なレポートを使用します。これらのレポートは自動生成されるだけでなく、データのグラフィカル表現を提供します。これには、レポートコマンドレット。 ただし、Windows PowerShell を使用している管理者は、レポートコマンドレットを使用して、Lync Online レポートからすぐに利用できないデータを返すことができます。 たとえば、レポートコマンドレットはセッションの継続時間 (各セッションが継続した時間) に関する情報を返します。 Lync Online レポートを使用して、個別のセッション期間を使用することはできません。 同様に、[毎日] ビューでは、Lync Online レポートには、過去14日間の情報のみが表示されます。 1日の日数の合計 (たとえば、4か月前の日付) を確認するには、レポートコマンドレットを使用します。

また、管理者は、「 [Excel を使用して office 365 レポートデータを取得する](http://msdn.microsoft.com/en-us/library/dn781442.aspx)」を参照してください。 Microsoft Excel の OData データ照会機能を使用して、カスタムの office 365 レポートを作成する方法について説明します。 カスタムレポートを使用すると、Office 365 レポートサービスから返されるデータ (およびデータ量) を指定することができます。 カスタムレポートを使用すると、データの並べ替えやグループ化の方法を指定したり、Office 365 管理センターに表示されない情報にアクセスしたりすることができます。

開発のバックグラウンドの管理者は、REST web サービスを使用して、Skype for Business Online 管理センターに表示されない情報を取得できます。 REST サービスは SOAP サービスと似ていますが、各テクノロジでクライアントとサーバーの間で XML データを転送する方法が用意されています。 ただし、REST サービスには SOAP サービスに関して少なくとも2つの利点があります。 1つ目は、ATOM シンジケーション形式と呼ばれる標準化された形式を使って XML データ転送を実行します。 これに対して、データ転送時の SOAP では、標準以外の形式を使用します。 また、REST は、GET と POST 以外の HTTP 動詞をブロックするネットワーク間でデータを転送することができます。

<div>

## <a name="see-also"></a>関連項目


[Lync Online レポート](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[Office 365 レポート Web サービス](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[Office 365 レポート Web サービスについて学習する](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Exchange Online のレポートコマンドレット](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[Excel を使用して Office 365 レポートデータを取得する](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

