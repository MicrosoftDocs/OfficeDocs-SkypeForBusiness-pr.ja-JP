---
title: 'Lync Server 2013: ローカル構成ストアのインストール'
description: 'Lync Server 2013: ローカル構成ストアをインストールします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf603704a8e1bdfbe71e0a9b064013d57bceda7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574063"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Lync Server 2013 でのローカル構成ストアのインストール

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-27_

これらの手順を実行する前に、ローカル管理者および RTCUniversalReadOnlyAdmin グループのメンバーの両方のドメインユーザーアカウントを使用してサーバーにログオンしていることを確認してください。

Lync Server 展開ウィザードを使用して操作できるようにするには、ローカル構成ストアがサーバー上に存在する必要があります。 ローカル構成ストアは、SQL Server Express のローカルインストールの後に作成される中央管理ストアの読み取り専用コピーです。 中央管理ストア自体が、Standard Edition サーバーまたは SQL Server Express ベースのデータベースにインストールされている既存の SQL Server データベースに追加されます。

<div>


> [!IMPORTANT]  
> このサーバーで Lync Server 2013 セットアップを実行していない場合は、Lync Server 2013 をインストールするためのドライブとパスの入力を求められます。 これにより、システムドライブ以外のドライブにインストールすることができます。組織で必要な場合、または容量に関する懸念がある場合。 [セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを新しい、利用可能なドライブに変更することができます。 このパスにセットアップファイル (OCSCore.msi を含む) をインストールすると、残りの Lync Server 2013 ファイルも同様に展開されます。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>ローカル構成ストアをインストールするには

1.  インストールメディアから、[setup amd64Setup.exe] を参照し、[ \\ \\ \\ **OK]** をクリックします。

2.  Microsoft Visual C++ 2012 の再頒布可能パッケージをインストールするように求めるメッセージが表示されたら、[ **はい**] をクリックします。

3.  [**Lync Server 2013 のインストール先**] ページで、[**OK**] をクリックします。

4.  [使用許諾 **契約書** ] ページで、ライセンス条項を確認し、[「 **使用許諾契約書**」の条項に同意します] を選択し、[ **OK** ] をクリックして続行することができます。

5.  [展開ウィザード] ページで、**[Lync Server システムのインストールまたは更新]** をクリックします。

6.  [**Lync Server 2013**] ページの [**ステップ 1: ローカル構成ストアのインストール**] で、[**実行**] をクリックします。

7.  [ **ローカル構成ストアのインストール** ] ページで、[ **中央管理ストアから直接取得** する] オプションがオンになっていることを確認し、[ **次へ**] をクリックします。

8.  ローカルサーバー構成のインストールが完了したら、[ **完了**] をクリックする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

