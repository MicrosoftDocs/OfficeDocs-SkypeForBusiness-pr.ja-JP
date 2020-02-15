---
title: パイロットプール展開の DNS レコードを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3b1f4b507887bc046cefddae9c924f0de1916b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41999122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロットプール展開の DNS レコードを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

Lync Server 2013 パイロットプールを展開する前に、DNS ホストをパイロットプールのエントリに更新する必要があります。 この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

**DNS ホスト A レコードを構成するには**

1.  ドメイン ネーム システム (DNS) サーバーで、[**スタート**]、[**管理ツール**]、および [**DNS**] の順にクリックします。

2.  ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされるドメインを右クリックします。

3.  [**新しいホスト (A または AAAA)**] をクリックします。

4.  [**名前**] をクリックし、Lync Server 2013 プールのホスト名を入力します (ドメイン名は、レコードが定義されている領域から、A レコードの一部として入力する必要はありません)。

5.  [ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。

6.  [**ホストの追加**] をクリックし、[**OK**] をクリックします。

7.  すべて終了したら [**完了**] をクリックします。

</div>

<span> </span>

</div>

</div>

</div>

