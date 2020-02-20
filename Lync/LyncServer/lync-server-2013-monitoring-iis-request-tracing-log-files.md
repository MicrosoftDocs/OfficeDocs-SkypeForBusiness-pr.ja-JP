---
title: 'Lync Server 2013: IIS 要求トレースログファイルの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1377eabd4ffc199fe7a9014d28f153aba10afa4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Lync Server 2013 での IIS 要求トレースログファイルの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Lync Server Mobility Service (Mcx) のインターネットインフォメーションサービス (IIS) 要求トレースを有効にすると、生成されるログファイルが1日あたり最大 3 gb のディスク領域を消費する可能性があります。 IIS トレースログは既定で有効になっています。 フロントエンドサーバーを監視して、ディスクの空き領域が不足しないようにする必要があります。

既定では、IIS は% SystemDrive%\\inetpub\\logs\\ログログにログファイルを格納します。

サーバー全体で IIS 要求トレースをオフにするには、コマンドラインで、次のように入力します。

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

**HttpLogging**コマンドの詳細については[https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927)、「」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

