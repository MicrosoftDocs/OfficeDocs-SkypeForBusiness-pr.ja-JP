---
title: パイロット プール展開の DNS レコードの構成
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
ms.openlocfilehash: 9014581901a80507e088a6eb1804fdfccaea0215
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロット プール展開の DNS レコードの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

Lync Server 2013 パイロットプールを展開する前に、パイロットプールの DNS ホストのエントリを更新する必要があります。 この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。

**DNS ホスト A レコードを構成するには**

1.  ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。

2.  ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  [**新しいホスト (A または AAAA)**] をクリックします。

4.  [**名前**] をクリックして、Lync Server 2013 プールのホスト名を入力します (ドメイン名は、レコードが定義されていて、A レコードの一部として入力する必要はありません)。

5.  [ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。

6.  [**ホストの追加**] をクリックし、[ **OK**] をクリックします。

7.  完了したら、[**完了**] をクリックします。

</div>

<span> </span>

</div>

</div>

</div>

