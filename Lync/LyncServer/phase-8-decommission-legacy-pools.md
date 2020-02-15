---
title: 'フェーズ 8: 従来のプールを使用停止にする'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6450e129d68aadcb0e79f38def3e89176ef93373
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a>フェーズ 8: 従来のプールを使用停止にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-08_

次のトピックでは、Lync Server 2010 の従来の展開での DNS エントリの更新、コンテンツ管理サーバーの移動、プールの使用停止、およびサーバーとプールの非アクティブ化と削除に関するガイダンスを提供します。 このセクションに記載された手順をすべて実行する必要はありません。 ドキュメントを読んで、どの使用停止の手順を実行すればよいかを判断してください。

Lync server 2010 サーバーとサーバーの役割を削除する方法、および Lync Server 2010 の展開を使用停止にするためのステップバイステップガイドについては、「」を参照してください[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)。「Microsoft lync server 2010 をアンインストールし、サーバーの役割を削除する」を参照してください。

<div>


> [!IMPORTANT]  
> 従来の環境を使用停止にする前に、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行およびアップグレードの詳細については、「」を参照してください。<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - <span></span>  
    [DNS SRV レコードを更新する](update-dns-srv-records.md)

  - <span></span>  
    [Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動する](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [電話会議ディレクトリを移動する](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [アーカイブサーバーの関連付けを削除する](remove-the-archiving-server-association.md)

  - <span></span>  
    [監視サーバーの関連付けを削除する](remove-the-monitoring-server-association.md)

  - <span></span>  
    [Enterprise Edition フロントエンドサーバーまたは Standard Edition フロントエンドサーバーを削除する](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [バックエンドサーバー上の SQL Server インスタンスとデータベースを削除する](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

