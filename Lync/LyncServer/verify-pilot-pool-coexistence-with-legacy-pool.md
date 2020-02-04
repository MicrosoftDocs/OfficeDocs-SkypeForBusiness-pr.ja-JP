---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>パイロット プールとレガシ プールの共存の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

パイロットプールを展開した後、管理ツールを使用してプール情報を表示し、2つのプールの共存を確認する必要があります。 Lync Server 2013 プールと従来のプールについては、「Lync Server 2013 コントロールパネル」および「トポロジビルダーツール」を使用する必要があります。

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Lync Server 2013 サービスが開始されたことを確認する

1.  Lync Server 2013 フロントエンドサーバーから、管理ツール\\の [サービス] アプレットに移動します。

2.  フロントエンドサーバーで次のサービスが実行されていることを確認します。

**Lync Server 2013 サービス**

![開始された Lync Server サービスの一覧](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "開始された Lync Server サービスの一覧")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを開く

Lync server 2013 展開のフロントエンドサーバーから、Lync Server 2013 コントロールパネルを開き、Lync Server 2010 プールを選択します。 手順を繰り返して Lync Server 2013 プールを開きます。

**Lync Server 2013 コントロールパネルを開く**

![[URL の選択] ダイアログボックス](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "[URL の選択] ダイアログボックス")

<div>


> [!IMPORTANT]  
> Lync server 2013 では、Lync Server コントロールパネルを使用する前に Silverlight のバージョン5に Silverlight をアップグレードする必要があります。



</div>

このトポロジには、Lync Server 2010 および Lync Server 2013 サーバーの役割が含まれています。

**Lync Server 2013 コントロールパネルのトポロジページ**

![Lync Server コントロールパネル-トポロジページ](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server コントロールパネル-トポロジページ")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Lync Server 2010 トポロジビルダーでトポロジを開かないようにします。

Lync Server 2010 トポロジビルダーを使用してトポロジを開こうとすると、以下のエラーが発生します。 トポロジを表示できるのは、Lync Server 2013 Topology Builder を使用している場合のみです。 Lync server 2013 と Lync Server 2010 の両方のプールを作成するには、Lync Server 2013 トポロジビルダーを使用する必要があります。

**Lync Server 2010 トポロジビルダーのエラーメッセージ**

![Lync Server Topology Builder MMC スナップエラー](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC スナップエラー")

</div>

</div>

<span> </span>

</div>

</div>

</div>

