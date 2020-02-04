---
title: 監視サーバーの関連付けの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f26a809056674c231212db3f824a2ecb7ce7ecd1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>監視サーバーの関連付けの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

監視サーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。 フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。 [トポロジビルダー] で、依存関係を消去してサーバーを削除すると、関連付けられているデータベースストアオブジェクトもトポロジビルダーで削除されることが通知されます。

<div>

## <a name="to-remove-the-monitoring-server-association"></a>監視サーバーの関連付けを削除するには

1.  Lync Server 2013 フロントエンドサーバーを開き、[トポロジビルダー] を開きます。

2.  Lync Server 2010 ノードに移動します。

3.  [トポロジビルダー] で、監視サーバーが定義されている場所に基づいて、 **Enterprise Edition のフロントエンドプール**、**標準エディションのフロントエンドサーバー**、または**ブランチサイト**を展開します。

4.  Survivable Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト名] を展開して、[ **Survivable branch アプライアンス**] を展開します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーインターフェイス内の<STRONG>Survivable Branch アプライアンス</STRONG>は、Survivable branch Server と Survivable branch Appliance の両方に適用されます。

    
    </div>

5.  監視サーバーと関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。

6.  [**プロパティの編集**] の [**全般**] で、[**関連付け**] の下の [**監視サーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。

7.  監視サーバーに関連付けられているその他のプール、サーバー、またはデバイスについて、前の手順を繰り返します。

8.  監視サーバーを右クリックし、[**削除**] をクリックします。

9.  [**依存**しているストアの削除] で、[ **OK]** をクリックします。

10. トポロジを公開し、レプリケーションの状態を確認し、必要に応じて Lync Server 展開ウィザードを実行します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

