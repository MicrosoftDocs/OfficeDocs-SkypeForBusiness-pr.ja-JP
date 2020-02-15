---
title: 監視サーバーの関連付けを削除する
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
ms.openlocfilehash: 746558cc47a7ed5ef7f59abe4e4f0771cc514d47
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>監視サーバーの関連付けを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

監視サーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。 依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。 トポロジビルダーで依存関係をクリアし、サーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。

<div>

## <a name="to-remove-the-monitoring-server-association"></a>監視サーバーの関連付けを削除するには

1.  Lync Server 2013 フロントエンドサーバーを開き、トポロジビルダーを開きます。

2.  [Lync Server 2010 ノードに移動します。

3.  トポロジビルダーで、監視サーバーが定義されている場所に基づいて、 **Enterprise Edition フロントエンドプール**、 **Standard Edition フロントエンドサーバー**、または**ブランチサイト**を展開します。

4.  存続可能 Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト] を展開して、[**存続可能ブランチアプライアンス**] を展開します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーインターフェイスの<STRONG>存続可能 Branch アプライアンス</STRONG>は、存続可能 branch Server と存続可能 branch Appliance の両方に適用されます。

    
    </div>

5.  監視サーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。

6.  [**プロパティの編集**] の [**全般**] で、[**関連付け**] の [**監視サーバーの関連付け**] チェック ボックスをオフにして、[**OK**] をクリックします。

7.  監視サーバーに関連付けられているその他のプール、サーバー、またはデバイスに対して、前の手順を繰り返します。

8.  監視サーバーを右クリックし、[**削除**] をクリックします。

9.  [**依存ストアの削除**] で、[**OK**] をクリックします。

10. トポロジを公開し、レプリケーションの状態を確認し、必要に応じて Lync Server 展開ウィザードを実行します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

