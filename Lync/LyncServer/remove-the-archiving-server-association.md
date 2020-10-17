---
title: アーカイブ サーバーの関連付けの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3d9de311668bd43d913b0f746470235060bafe3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499974"
---
# <a name="remove-the-archiving-server-association"></a>アーカイブ サーバーの関連付けの削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

アーカイブサーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。 依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。 依存関係をクリアし、トポロジビルダーでサーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。

<div>

## <a name="to-remove-the-archiving-server-association"></a>アーカイブサーバーの関連付けを削除するには

1.  Lync Server 2013 フロントエンドサーバーを開き、トポロジビルダーを開きます。

2.  [Lync Server 2010 ノードに移動します。

3.  トポロジビルダーで、アーカイブサーバーが定義されている場所に基づいて、 **Enterprise Edition フロントエンドプール**、 **Standard Edition フロントエンドサーバー**、または **ブランチサイト**を展開します。

4.  存続可能 Branch Server が関連付けられている場合は、[ **ブランチサイト**] を展開し、[ブランチサイト] を展開して、[ **存続可能ブランチアプライアンス**] を展開します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーインターフェイスの<STRONG>存続可能 Branch アプライアンス</STRONG>は、存続可能 branch Server と存続可能 branch Appliance の両方に適用されます。

    
    </div>

5.  アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[ **プロパティの編集**] をクリックします。

6.  [ **プロパティの編集**] の [ **全般**] で、[ **関連付け**] の [ **アーカイブサーバーの関連付け** ] チェックボックスをオフにして、[ **OK]** をクリックします。

7.  削除するアーカイブサーバーに関連付けられているその他のプール、サーバー、またはデバイスに対して、前の手順を繰り返します。

8.  アーカイブサーバーを右クリックし、[ **削除**] をクリックします。

9.  [**依存ストアの削除**] で、[**OK**] をクリックします。

10. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

