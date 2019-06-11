---
title: 構成の設定の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd35ed2d153bb33f93f6533e9eacb0ffab7788f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>構成の設定の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-06_

中央管理ストアが配置されている内部コンピューターまたは任意のドメイン上で Lync Server 2013 **CsManagementStoreReplicationStatus**コマンドレットを実行して、構成情報のレプリケーションをエッジサーバーに対して検証することができます。Lync Server 2013 コアコンポーネント (OcsCore) がインストールされている参加したコンピューター。

初期結果では、レプリケーションに "True" ではなく "False" と表示されることがあります。 その場合は、 **CsManagementStoreReplication**コマンドレットを実行して、 **CsManagementStoreReplicationStatus**をもう一度実行する前に複製処理が完了するまで待ちます。

</div>

<span> </span>

</div>

</div>

</div>

