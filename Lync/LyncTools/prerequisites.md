---
title: 前提条件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 394f73c83f1981e4c4ee1528c1623f6424d2a85a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-19_

Lync Server 2013 のストレスとパフォーマンスのツールを実行するためには、さまざまなハードウェア、ソフトウェア、システム構成の要件があります。

<div>

## <a name="client-hardware-requirements"></a>クライアントハードウェア要件

Lync server 2013 の展開で Lync Server 2013 ストレスおよびパフォーマンスツールを実行するには、ロードをシミュレートするすべての4500ユーザーに対して、次の最小ハードウェア要件を満たす少なくとも1つの専用コンピューターが必要です。

  - 1 ギガビットのネットワーク アダプター

  - 8 GB ram

  - 2デュアルコアセントラルプロセッシングユニット (Cpu)

</div>

<div>

## <a name="client-software-requirements"></a>クライアントソフトウェア要件

Lync server 2013 のストレスとパフォーマンスツールを Lync Server 2013 の展開で実行するために、サポートされているオペレーティングシステムは次のとおりです。

  - Windows Server 2012 オペレーティングシステム

  - Windows Server 2008 オペレーティングシステム (64 ビット版)

クライアントコンピューターは、次のソフトウェア要件を満たしている必要があります。

  - [Microsoft .Net Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212)ランタイムがインストールされている必要があります。

  - Windows Server 2008/Windows Server 2012 では、デスクトップエクスペリエンス機能を有効にする必要があります。

  - [Microsoft Visual C++ 2012 再頒布可能パッケージ](http://go.microsoft.com/fwlink/?linkid=143216)(x64) がインストールされている必要があります。

  - 完全に構成された Lync Server 2013 の展開。

<div>


> [!IMPORTANT]  
> Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 4.0 ライブラリはインストールパッケージに含まれているため、UCMA は不要であり、クライアントコンピューターにインストールされていない必要があります。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>構成要件

Lync Server 2013 のストレスとパフォーマンスツールを実行するコンピューターは、次の要件に従って構成する必要があります。

1.  ドメインまたはローカル管理者グループのメンバーとしてログオンしている必要があります。

2.  Lync server 2013 のストレスとパフォーマンスツール (LyncPerfTool) は、Lync Server 2013 コンポーネントも実行しているコンピューターでは実行できません。

3.  フロントエンドサーバーまたはユーザーアカウントが存在する Standard Edition サーバーで Lync Server 2013 ユーザー作成ツール (Useritemscontrol Tool) を実行する必要があります。 ツールが複数回実行される場合、Microsoft ユニファイドコミュニケーションを有効にしている各ユーザーは、一意の電話番号を持っている必要があります。

4.  ページファイルのサイズは、システムで管理されているか、システムの RAM の量の1.5 倍以上である必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

