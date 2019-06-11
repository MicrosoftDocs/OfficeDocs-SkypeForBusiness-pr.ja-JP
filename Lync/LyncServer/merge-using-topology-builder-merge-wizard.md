---
title: トポロジビルダーの結合ウィザードを使用してマージする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>トポロジビルダーの結合ウィザードを使用してマージする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

1.  トポロジビルダーを使用して、既存の展開をダウンロードします。

2.  [**アクション**] メニューで、[ **Office Communications Server 2007 R2 の結合**] を選択します。

3.  [ **次へ**] をクリックします。

4.  [ **Edge セットアップの指定**] で [**追加**] をクリックします。
    
    ![トポロジの結合ウィザード、[Edge セットアップ] ページを指定する](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "トポロジの結合ウィザード、[Edge セットアップ] ページを指定する")  

5.  [ **Edge の種類の指定**] で、エッジサーバー構成の種類を入力し、[**次へ**] をクリックします。 この例では、[**単一エッジサーバー** ] オプションを使用します。
    
    <div>
    

    > [!IMPORTANT]  
    > 拡張された<STRONG>エッジ展開</STRONG>は、サポートされている構成ではありません。 展開された<STRONG>エッジサーバー</STRONG>は、最初に<STRONG>1 つのエッジサーバー</STRONG>または負荷分散された<STRONG>統合エッジ</STRONG>サーバーに変換する必要があります。

    
    </div>

6.  [**内部エッジ設定の指定**] で、必要に応じて、エッジプールの内部 FQDN とポートに関連する情報を入力し、[**次へ**] をクリックします。
    
    ![内部の端の設定ダイアログを指定する](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "内部の端の設定ダイアログを指定する")  

7.  [**外部エッジの指定**] で、エッジサーバーの web 会議の FQDN 情報を入力します。
    
    <div>
    

    > [!IMPORTANT]  
    > [<STRONG>次へ</STRONG>] をクリックする前に、この手順の次の手順を実行します。 この手順を見逃さないようにすることは非常に重要です。

    
    </div>

8.  フェデレーション用の従来の Office Communications Server 2007 R2 Edge サーバーの使用を計画している場合は、[**このエッジプールをフェデレーションとパブリック IM 接続に使用**する] チェックボックスをオンにします。 複数のエッジサーバーが展開されている場合は、そのうちの1つのみがフェデレーション対象として有効になります。 このチェックボックスをオフにして、後でフェデレーションを有効にする場合は、トポロジビルダーの結合ウィザードを実行して、もう一度トポロジを公開する必要があります。
    
    ![[エッジサーバー] ダイアログ、[外部エッジの指定] ページ](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "[エッジサーバー] ダイアログ、[外部エッジの指定] ページ")  

9.  [**次ホップの指定**] で、環境内の次のホップ位置の完全修飾ドメイン名 (FQDN) を入力します。 [**完了**] をクリックします。
    
    [![エッジサーバー] ダイアログボックス、[次ホップの指定] ページ][(images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "エッジサーバー] ダイアログボックス、[次ホップの指定] ページ")  

10. Office Communications Server 2007 R2 Edge サーバーがすべて追加されている場合は、[ **Edge セットアップの指定**] で [**次へ**] をクリックします。 追加する Office Communications Server 2007 R2 Edge サーバーが他にもある場合は、手順4からこの手順を繰り返します。

11. [**内部 sip ポートの指定**] で、既定の設定 (つまり、既定の sip ポートを変更していない場合) を選択します。 既定のポート5061を使用していない場合は、必要に応じて変更して、[**次へ**] をクリックします。

12. [**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。

13. ウィザードのページで、トポロジの結合が正常に完了したことを確認します。

14. [**状態**] 列で、値が**成功**していることを確認し、[**完了**] をクリックします。

15. [Topology Builder] の左側のウィンドウに、 **BackCompatSite**が表示されます。これは、Office Communications Server 2007 R2 環境が Lync Server 2013 に統合されていることを示します。
    
    ![結合されたトポロジを示すトポロジビルダー](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "結合されたトポロジを示すトポロジビルダー")  

16. [**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。

17. **発行ウィザード**が完了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 従来のポリシー設定が Lync Server 2013 にインポートされるようにするには、次のトピック「<A href="import-policies-and-settings.md">ポリシーと設定のインポート</A>」を完了しておくことが重要です。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

