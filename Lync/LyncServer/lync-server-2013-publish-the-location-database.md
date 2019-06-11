---
title: 'Lync Server 2013: 位置情報データベースを発行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afc13a67ccdad3d27328107e095f1bffa66fdcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Lync Server 2013 からロケーションデータベースを発行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。

詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - **公開-CsLisConfiguration**

緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、公衆交換電話網 (PSTN) の通信事業者の自動ロケーション識別 (ALI) データベースに ELIN をアップロードする必要があります。 ELIN レコードに特定の形式を使用するように PSTN の通信事業者が求める場合があります。 詳細については、PSTN の通信事業者に問い合わせてください。 場所情報サービスデータベースからレコードをエクスポートし、必要に応じて書式設定することができます。

<div>

## <a name="to-publish-the-location-database"></a>場所データベースを公開するには

  - Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

  - 場所データベースを公開するには、次のコマンドレットを実行します。
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

