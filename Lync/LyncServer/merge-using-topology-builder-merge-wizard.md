---
title: トポロジビルダーマージウィザードを使用したマージ
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>トポロジビルダーマージウィザードを使用したマージ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

1.  トポロジ ビルダーを使用して既存の展開をダウンロードします。

2.  [**操作**] メニューの [**Office Communications Server 2007 R2 トポロジのマージ**] をクリックします。

3.  [**次へ**] をクリックします。

4.  [**エッジ セットアップの指定**] で、[**追加**] をクリックします。
    
    ![トポロジのマージウィザード、[エッジセットアップの指定] ページ](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "トポロジのマージウィザード、[エッジセットアップの指定] ページ")  

5.  [**エッジの種類の指定**] で、エッジ サーバー構成の種類を入力し、[**次へ**] をクリックします。この例では [**単一エッジ サーバー**] オプションを使用します。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>拡張エッジ展開</STRONG>の構成はサポートされていません。まず、<STRONG>拡張エッジ サーバー</STRONG>を<STRONG>単一エッジ サーバー</STRONG>または<STRONG>負荷分散された統合エッジ</STRONG> サーバーに変換する必要があります。

    
    </div>

6.  [**内部エッジ設定の指定**] で、必要に応じてエッジプールの内部 FQDN およびポートに関連する情報を入力し、[**次へ**] をクリックします。
    
    ![内部エッジ設定の指定ダイアログ](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "内部エッジ設定の指定ダイアログ")  

7.  [**外部エッジの指定**] で、エッジ サーバーの Web 会議 FQDN 情報を入力します。
    
    <div>
    

    > [!IMPORTANT]  
    > [<STRONG>次へ</STRONG>] をクリックする前に、この手順の次のステップを行います。このステップを必ず行うことが非常に重要です。

    
    </div>

8.  フェデレーションに従来の Office Communications Server 2007 R2 エッジサーバーを使用することを計画している場合は、[**このエッジプールを使用してフェデレーションとパブリック IM 接続を使用**する] チェックボックスをオンにします。 複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。 このボックスをオンにせず、フェデレーションを有効にすることを後で決定した場合、トポロジ ビルダー結合ウィザードを実行してから、トポロジを再び公開する必要があります。
    
    ![エッジサーバーダイアログ、[外部エッジの指定] ページ](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "エッジサーバーダイアログ、[外部エッジの指定] ページ")  

9.  [**次ホップの指定**] に、環境内の次ホップの場所の完全修飾ドメイン名 (FQDN) を入力します。 [**完了**] をクリックします。
    
    ![[エッジサーバー] ダイアログボックス、[次ホップの指定] ページ](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "[エッジサーバー] ダイアログボックス、[次ホップの指定] ページ")  

10. [**エッジセットアップの指定**] で、すべての Office Communications Server 2007 R2 エッジサーバーが追加されている場合は、[**次へ**] をクリックします。 追加する Office Communications Server 2007 R2 エッジサーバーが多い場合は、手順4からこの手順を繰り返します。

11. [**内部 sip ポートの指定**] で、既定の設定 (つまり、既定の sip ポートを変更しなかった場合) を選択します。 既定のポート5061を使用していない場合は、必要に応じて変更し、[**次へ**] をクリックします。

12. [**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。

13. ウィザードのページでトポロジのマージが成功したことを確認します。

14. [**状態**] 列の値が "**成功**" になっていることを確認し、[**完了**] をクリックします。

15. トポロジビルダーの左側のウィンドウに、 **BackCompatSite**が表示されます。これは、Office Communications Server 2007 R2 環境が Lync Server 2013 と統合されていることを示しています。
    
    ![トポロジビルダーに結合されたトポロジが表示されている](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "トポロジビルダーに結合されたトポロジが表示されている")  

16. [**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。

17. **公開ウィザード**の実行が完了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 次のトピック「<A href="import-policies-and-settings.md">ポリシーと設定をインポート</A>する」を完了して、従来のポリシー設定が Lync Server 2013 にインポートされていることを確認することが重要です。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

