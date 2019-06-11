---
title: 'Lync Server 2013: 更新したトポロジの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f3be1443f98444712a66942417e1812181efe7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Lync Server 2013 での更新したトポロジの公開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

トポロジビルダーでトポロジを更新した後は、常設チャットサーバーを構成して使用する前に、トポロジを中央管理ストアに発行する必要があります。 このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。

<div>

## <a name="to-publish-an-updated-topology"></a>更新されたトポロジを公開するには

トポロジを公開する前に、常設チャットサーバー用のデータベースをインストールします。 [**アクション**]、[**データベースのインストール**] の順に選択して、トポロジビルダーを使用してデータベースをインストールします。

1.  Lync Server 2013 を実行しているか、Lync Server 管理ツールがインストールされているコンピューターの場合は、**ドメイン管理**者グループと**RTCUniversalServerAdmins**グループの両方のメンバーであるアカウントを使用してログオンします。フルコントロールがあります。常設チャットサーバーファイルストアで使用するアクセス許可 (読み取り、書き込み、変更) (Topology Builder では、必要な随意アクセス制御リスト (Dacl))、または同等のユーザー権限を持つアカウントを構成することができます。

2.  トポロジビルダーを起動します。 [**既存の展開からトポロジをダウンロード**] を選択するか、**ローカルファイル**をローカルで保存した場合は、[トポロジを開く] をクリックします。

3.  コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**トポロジの公開**] をクリックします。

4.  [**トポロジの公開**] ページで、[**次へ**] をクリックします。

5.  [**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > トポロジを公開した後は、コンテンツをアーカイブする前に、常設チャットサーバーのサポートを構成する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

