---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c9bc007eda604ce4894497db4a6ef334315d28
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロット プール展開の DNS レコードの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

Lync Server 2013 パイロットプールを展開する前に、パイロットプールの DNS ホストのエントリを更新する必要があります。 この手順を正常に完了するには、少なくとも Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

**DNS ホスト A レコードを構成するには**

1.  ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。

2.  ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  [**新しいホスト (A または AAAA)**] をクリックします。

4.  [**名前**] をクリックし、プールのホスト名を入力します (ドメイン名は、レコードが定義されているゾーンから、A レコードの一部として入力する必要はありません)。

5.  [ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。

6.  [**ホストの追加**] をクリックし、[ **OK**] をクリックします。

7.  完了したら、[**完了**] をクリックします。

</div>

<span> </span>

</div>

</div>

</div>

