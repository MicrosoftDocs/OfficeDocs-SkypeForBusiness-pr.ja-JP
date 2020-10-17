---
title: SCOM 監視の構成
description: SCOM 監視を構成します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c93e10c705a1a1e08972d7534e00a33c472d23a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542993"
---
# <a name="configure-scom-monitoring"></a>SCOM 監視の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2013 に移行した後で、Lync Server 2013 を System Center Operations Manager と連携するように構成するには、いくつかのタスクを完了する必要があります。

  - 中央検出ロジックを管理するために選択したサーバーに Lync Server 2010 の更新プログラムを適用します。

  - 中央検出候補サーバーのレジストリ キーを更新する。

  - プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補」ノードを上書きします。

各タスクを実行する手順を次に示します。

**中央検出ロジックを管理するために選択したサーバーに Lync Server 2010 の更新プログラムを適用します。**

1.  System Center Operations Manager エージェント ファイルがインストールされ、候補検出ノードとして構成されているサーバーを選択します。

2.  このサーバーに Lync Server 2010 の更新プログラムを適用します。 「 [Lync Server 2010 の更新プログラムの適用](apply-lync-server-2010-updates.md)」を参照してください。

**中央検出候補サーバーのレジストリ キーを更新する。**

1.  中央検出ロジックを管理することを選択したサーバーで、Windows PowerShell コマンドウィンドウを開きます。

2.  コマンド ラインで、次のように入力します。
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > レジストリを編集すると、"レジストリ キーが既に存在する場合はコマンドが失敗する" というエラーが発生することがあります。このエラーは無視しても問題ありません。

    
    </div>

**プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補監視ノードの候補を上書きします。**

1.  System Center Operations Manager コントロールがインストールされているコンピューターで、[**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] を選択します。

2.  [**スコープの変更**] をクリックします。

3.  [**管理パック オブジェクトのスコープ設定**] ページで、[**LS Discovery Candidate**] を選択します。

4.  前の手順で選択した候補サーバーの名前の [**LS Discovery Candidate Effective Value**] を上書きします。

最後に、変更を確定するには、System Center Operations Manager のルート管理サーバーで状態サービスを再起動します。

</div>

<span> </span>

</div>

</div>

</div>

