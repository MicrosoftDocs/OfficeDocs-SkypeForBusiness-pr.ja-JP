---
title: 構成の設定を確認する
description: 構成設定を確認します。
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
ms.openlocfilehash: d7bb1135e95dafe51e906768fe0f4f0d57bf2d6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573113"
---
# <a name="verify-configuration-settings"></a>構成の設定を確認する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-06_

中央管理ストアが配置されている内部コンピューターで、または Lync Server 2013 コアコンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、Lync **server 2013 コマンド** レットを実行することで、構成情報のレプリケーションを検証できます。

最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。 その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。

</div>

<span> </span>

</div>

</div>

</div>

