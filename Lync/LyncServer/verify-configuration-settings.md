---
title: 構成の設定を確認する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c98ec6387353e60890653a0369107c126f8eeb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>構成の設定を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-06_

中央管理ストアが配置されている内部コンピューターで、または Lync Server 2013 コアコンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、Lync **server 2013 コマンド**レットを実行することで、構成情報のレプリケーションを検証できます。

最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。 その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。

</div>

<span> </span>

</div>

</div>

</div>

