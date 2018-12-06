---
title: ユーザーへの Lync Server アーカイブ ポリシーの適用
TOCTitle: ユーザーへの Lync Server アーカイブ ポリシーの適用
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48273040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザーへの Lync Server アーカイブ ポリシーの適用

 

_**トピックの最終更新日:** 2012-10-10_

Lync Server ユーザー ポリシーを作成したら、それを有効にする前に、Lync Server 2013 に所属する特定のユーザーまたはユーザー グループに適用する必要があります。特定のユーザー用のユーザー ポリシーの作成の詳細については、「展開」のドキュメントの「[Lync Server でのアーカイブ用のユーザー ポリシーの作成と構成](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)」を参照してください。

グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層を含むアーカイブ ポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」 を参照してください。

> [!NOTE]  
> アーカイブを構成して使用するためには、まずアーカイブを展開する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-deploying-archiving.md">Lync Server 2013 でのアーカイブの展開</a>」を参照してください。<br />
> 展開で Microsoft Exchange の統合を有効にした場合、Exchange 2013 に所属し、メールボックスがインプレース保持になっているユーザーに対してアーカイブが有効となるかどうかが Exchange のインプレース保持ポリシーによって制御されます。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。<br />
> アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-configuring-archiving-options.md">アーカイブ オプションの構成</a>」を参照してください。


## Lync Server アーカイブ ポリシーをユーザーに適用するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server 2013 コントロール パネルを開きます。Lync Server 2013 コントロール パネルを起動するさまざまな方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックして、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**Lync Server ユーザーの編集**\] の \[**アーカイブ ポリシー**\] で、適用するアーカイブ ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > [<strong>&lt;自動&gt;</strong>] 設定では、既定のサーバー インストールの設定が適用されます。 これらの設定はサーバーにより自動的に適用されます。


6.  \[**確定**\] をクリックします。

