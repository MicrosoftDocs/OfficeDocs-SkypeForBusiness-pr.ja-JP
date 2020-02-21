---
title: 'Lync Server 2013: 場所データベースの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b773e5332ba05d20da9ece0b7ecb521d664e3b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Lync Server 2013 からの場所データベースの公開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。

詳細については、次のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。

  - **Export-cslisconfiguration**

緊急位置識別番号 (ELIN) ゲートウェイを使用する場合、ELINs を公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードする必要もあります。 PSTN キャリアでは、ELIN レコードに特定の形式を使用する必要がある場合があります。 詳細については、PSTN キャリアにお問い合わせください。 場所情報サービスデータベースからレコードをエクスポートし、必要に応じて書式設定することができます。

<div>

## <a name="to-publish-the-location-database"></a>場所データベースを公開するには

  - Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

  - 次のコマンドレットを実行して、場所データベースを公開します。
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

