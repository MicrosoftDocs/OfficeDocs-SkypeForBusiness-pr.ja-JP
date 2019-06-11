---
title: 'Lync Server 2013: IIS 要求のトレースログファイルを監視する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Lync Server 2013 で IIS 要求トレースのログファイルを監視する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Lync Server Mobility Service (Mcx) のインターネットインフォメーションサービス (IIS) 要求のトレースを有効にすると、生成されたログファイルは1日に最大 3 gb のディスク領域を消費する可能性があります。 IIS トレースログは既定で有効になっています。 フロントエンドサーバーを監視して、ディスク領域が不足していないことを確認する必要があります。

既定では、IIS は、ログファイルを% SystemDrive\\%\\inetpub\\logs ログログに保存します。

サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

**HttpLogging**コマンドの詳細については[http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)、を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

