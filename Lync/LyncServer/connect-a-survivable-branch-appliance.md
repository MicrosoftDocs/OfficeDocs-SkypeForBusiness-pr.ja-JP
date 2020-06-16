---
title: 存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスの接続

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。 フロントエンドプールが Lync Server 2013 に移行される場合は、プールがアップグレードされている間は、SBA を Lync Server 2010 のフロントエンドプールから関連付け解除する必要があります。プールが Lync Server 2013 に移行されると、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。 これには、トポロジビルダーの従来の Lync Server 2010 トポロジから SBA を削除してから、SBA を Lync Server 2013 トポロジに追加する必要があります。 従来の Lync Server 2010 SBA に所属するユーザーは、SBA をトポロジから削除する前に、別のフロントエンドプールに移動する必要があります。 SBA が Lync Server 2013 トポロジに追加されると、それらのユーザーは SBA に戻ることができます。 これらの手順の概要を次に示します。

1.  従来の SBA Lync Server 2010 に所属するブランチユーザーを別のフロントエンドプールに移動します。

2.  SBA を従来の Lync Server 2010 トポロジから削除して、既存のフロントエンドプールをバックアップレジストラーとして切断します。

3.  SBA を Lync Server 2013 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。

4.  ブランチユーザーを新しい Lync Server 2013 SBA に移動します。

**Lync Server 2010 SBA ブランチ サイトをトポロジに追加する**

1.  **トポロジ ビルダー**を開きます。

2.  左側のウィンドウで、**[ブランチ サイト]** を右クリックし、**[新しいブランチ サイト]** をクリックします。

3.  **[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。

4.  (オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。

5.  **[次へ]** をクリックします。

6.  (オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。
    
    1.  **[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。
    
    2.  **[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。
    
    3.  **[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。

7.  **[次へ]** をクリックし、次のいずれかを実行します。
    
    1.  If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.

8.  従来の Lync Server 2010 SBA を Lync Server 2013 フロントエンドプールに関連付けるには、次のようにします。
    
    1.  作成したブランチ サイトを展開します。
    
    2.  **[Lync Server 2010]** を右クリックして、**[新規]** をクリックします。
    
    3.  **[存続可能ブランチ アプライアンス]** をクリックします。

9.  ウィザードが開くのでその指示に従います。 ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 存続可能ブランチアプライアンスは、Lync Server 2010 の監視ストアにのみ関連付けることができます。

    
    </div>

10. このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。

11. トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。

</div>

<span> </span>

</div>

</div>

</div>

