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
ms.openlocfilehash: 9a4f10cb1bdf5733dbe54519325475871be10564
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-19_

Lync Server 2013 ストレスおよびパフォーマンスツールを実行するには、さまざまなハードウェア、ソフトウェア、およびシステム構成の要件があります。

<div>

## <a name="client-hardware-requirements"></a>クライアントハードウェアの要件

Lync server 2013 のストレスおよびパフォーマンスツールを Lync Server 2013 展開で実行するには、負荷をシミュレートするすべての4500ユーザーに対して、次の最小ハードウェア要件を満たしている少なくとも1つの専用コンピューターが必要です。

  - 1ギガビットのネットワークアダプター

  - 8 GB の ram

  - 2つのデュアルコア中央処理装置 (Cpu)

</div>

<div>

## <a name="client-software-requirements"></a>クライアントソフトウェアの要件

Lync server 2013 のストレスおよびパフォーマンスツールを Lync Server 2013 展開で実行するために、サポートされているオペレーティングシステムは次のとおりです。

  - Windows Server 2012 オペレーティングシステム

  - Windows Server 2008 オペレーティングシステム (64 ビット版)

クライアントコンピューターは、次のソフトウェア要件を満たしている必要があります。

  - [Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212)ランタイムがインストールされている必要があります。

  - Windows Server 2008/Windows Server 2012 では、デスクトップ環境機能を有効にする必要があります。

  - [Microsoft Visual C++ 2012 再頒布可能パッケージ](https://go.microsoft.com/fwlink/?linkid=143216)(x64) がインストールされている必要があります。

  - 完全に構成された Lync Server 2013 の展開。

<div>


> [!IMPORTANT]  
> Microsoft 統合コミュニケーション管理 API (UCMA) 4.0 ライブラリはインストールパッケージに含まれているため、UCMA は必要ではなく、クライアントコンピューターにインストールする必要はありません。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>構成要件

Lync Server 2013 ストレスおよびパフォーマンスツールを実行するコンピューターは、次の要件に従って構成する必要があります。

1.  ドメインまたはローカルの管理者グループのメンバーとしてログオンしている必要があります。

2.  Lync server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) は、Lync Server 2013 コンポーネントも実行しているコンピューターでは実行できません。

3.  ユーザーアカウントが存在するフロントエンドサーバーまたは Standard Edition サーバーで Lync Server 2013 ユーザー作成ツール (Userプロビジョニングツール) を実行する必要があります。 ツールを複数回実行する場合、Microsoft ユニファイドコミュニケーションが有効になっている各ユーザーは、一意の電話番号を持っている必要があります。

4.  ページファイルのサイズは、システムで管理されているか、システムの RAM の容量の少なくとも1.5 倍になっている必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

