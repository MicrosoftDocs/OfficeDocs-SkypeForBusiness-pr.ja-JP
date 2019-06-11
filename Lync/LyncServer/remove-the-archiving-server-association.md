---
title: アーカイブ サーバーの関連付けの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>アーカイブ サーバーの関連付けの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

アーカイブサーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。 フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。 依存関係を消去して、トポロジビルダーでサーバーを削除すると、トポロジビルダーの関連付けられたデータベースストアオブジェクトも削除されることが通知されます。

<div>

## <a name="to-remove-the-archiving-server-association"></a>アーカイブサーバーの関連付けを削除するには

1.  Lync Server 2013 フロントエンドサーバーを開き、[トポロジビルダー] を開きます。

2.  Lync Server 2010 ノードに移動します。

3.  [トポロジビルダー] で、アーカイブサーバーが定義されている場所に基づいて、 **Enterprise Edition のフロントエンドプール**、**標準エディションのフロントエンドサーバー**、または**ブランチサイト**を展開します。

4.  Survivable Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト名] を展開して、[ **Survivable branch アプライアンス**] を展開します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーインターフェイス内の<STRONG>Survivable Branch アプライアンス</STRONG>は、Survivable branch Server と Survivable branch Appliance の両方に適用されます。

    
    </div>

5.  アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。

6.  [**プロパティの編集**] の [**全般**] で、[**関連付け**] の下の [**アーカイブサーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。

7.  削除するアーカイブサーバーに関連付けられているその他のプール、サーバー、またはデバイスについて、前の手順を繰り返します。

8.  アーカイブサーバーを右クリックし、[**削除**] をクリックします。

9.  [**依存**しているストアの削除] で、[ **OK]** をクリックします。

10. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

