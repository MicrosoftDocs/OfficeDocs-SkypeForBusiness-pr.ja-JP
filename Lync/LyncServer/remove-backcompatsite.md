---
title: BackCompatSite の削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f431ada6c48e830cfa06af98f5937cae9fa4d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>BackCompatSite の削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

すべてのプールを非アクティブ化し、すべてのエッジ サーバーをアンインストールした後、トポロジ ビルダー結合ウィザードを実行して、[**BackCompatSite**] を削除します。

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>トポロジ ビルダーで BackCompat サイトを削除するには

1.  トポロジ ビルダーから既存の展開を開きます。

2.  [**操作**] メニューの [**Office Communications Server 2007 R2 トポロジのマージ**] をクリックします。

3.  [**次へ**] をクリックして続行します。

4.  [**レガシ エッジの指定**] ページで、エッジ サーバーの一覧が空になっていることを確認します。一覧が空でない場合は、[**削除**] ボタンを使用してすべてのレガシ エッジ サーバーを削除し、[**次へ**] をクリックします。
    
    ![トポロジのマージウィザード、[エッジセットアップの指定] ページ](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "トポロジのマージウィザード、[エッジセットアップの指定] ページ")  

5.  [**内部 SIP ポートの指定**] ページで、[**次へ**] をクリックします。

6.  [**概要**] ページで、[**次**へ] をクリックして、従来のサイトを削除するためのトポロジのマージを開始します。

7.  [**状態**] 列の値が "**成功**" になっていることを確認し、[**完了**] をクリックしてウィザードを閉じます。

8.  トポロジ ビルダーの左側のウィンドウで [BackCompatSite] を展開し、サーバーが表示されないことを確認します。

9.  [**BackCompatSite**] を右クリックし、[**削除**] をクリックします。

10. **トポロジ ビルダー**で、最上位ノードの [**Lync Server**] を選択します。

11. [**操作**] メニューの [**トポロジの公開**] を選択し、[**次へ**] をクリックします。

12. **公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

