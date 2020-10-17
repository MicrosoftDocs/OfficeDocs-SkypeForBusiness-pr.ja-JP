---
title: 'Lync Server 2013: 更新されたトポロジの公開'
description: 'Lync Server 2013: 更新されたトポロジを公開します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c27cca2eae86eadaf1ff37e2c3520eaec3f86c98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571693"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Lync Server 2013 で更新されたトポロジを公開する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

トポロジビルダーでトポロジを更新した後は、常設チャットサーバーを構成して使用する前に、トポロジを中央管理ストアに公開する必要があります。 このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。

<div>

## <a name="to-publish-an-updated-topology"></a>更新されたトポロジを公開するには

トポロジを公開する前に、常設チャットサーバーのデータベースをインストールします。 トポロジビルダーを使用してデータベースをインストールするには、[ **アクション** ] を選択して **データベースをインストール**します。

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、 **Domain Admins** グループと **RTCUniversalServerAdmins** グループの両方のメンバーであり、常設チャットサーバーのファイルストアに使用されるファイルストアに対するフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用してログオンします (これにより、トポロジビルダーが必要な随意アクセス制御リスト (dacl) を構成できるようになります)。

2.  トポロジ ビルダーを開始します。 [**既存の展開からトポロジをダウンロードする**] を選択するか、トポロジがローカルに保存されている場合は [**ローカル ファイルからトポロジを開く**] を選択します。

3.  コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[ **トポロジの公開**] をクリックします。

4.  [**トポロジの公開**] ページで、[**次へ**] をクリックします。

5.  [**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > トポロジを公開した後、コンテンツをアーカイブする前に、常設チャットサーバーのサポートを構成する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

