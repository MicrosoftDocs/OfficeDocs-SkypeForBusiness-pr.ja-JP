---
title: 'Lync Server 2013: 仲介サーバーのファイルのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7fd5613b39fd17724c9b62152f9d9401fbc072
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498594"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 での仲介サーバーのファイルのインストール

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-06_

この手順を正常に完了するには、少なくとも、ローカル管理者および少なくとも RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメインユーザーとしてサーバーにログオンしている必要があります。

このトピックの手順を使用して、Lync server 2013 展開ウィザードを実行し、トポロジビルダーを使用してプールを定義して発行したときに、仲介サーバープールに追加したコンピューターに仲介サーバーのファイルをインストールします。 ファイル仲介サーバーをインストールするときは、仲介サーバープール内の各コンピューターが必要とする証明書をインストールして割り当てます。

このサイトでは、フロントエンドプールまたは Standard Edition サーバーに併置された仲介サーバーを既に展開している場合は、このトピックを省略してもかまいません。その代わりに、 [Lync server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)を続行します。

<div>


> [!NOTE]  
> このトピックでは、「展開」のドキュメントの「Lync server 2013 のトポロジビルダーでの <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">仲介サーバーの定義</A> 」および「 <A href="lync-server-2013-publish-the-topology.md">lync server 2013 でのトポロジの公開</A> 」の説明に従って、スタンドアロンの仲介サーバープールを既に定義して公開していることを前提としています。さらに、仲介サーバープール内のコンピューターが、lync Server 2013 の「 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">エンタープライズ voip の前提</A> 条件」で説明されている前提条件と、 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync server 2013 のエンタープライズ voip のセキュリティおよび構成の前提</A>条件を満たしていることを確認していること。



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>スタンドアロンの仲介サーバープールのファイルをインストールするには

1.  インストールメディアから、[ \<installation media\> ** \\ Setup \\ amd64 \\Setup.exe**] を右クリックし、[**管理者として実行**] をクリックします。

2.  [ **インストール先** ] ページで、[ **OK**] をクリックします。

3.  [ **使用許諾契約書** ] ページで、[ **同意**します] をクリックし、[ **OK**] をクリックします。 (続行する必要があります。)

4.  [ **Lync server 2010 展開ウィザード** ] ページで、[ **lync Server システムのインストールまたは更新**] をクリックします。

5.  [ **ステップ 1: ローカル構成ストアのインストール**] の横にある [ **実行**] をクリックし、画面の指示に従います。

6.  [ **中央管理ストアのローカルレプリカの構成** ] ページで、既定の [ **中央管理ストアから直接取得**する] をそのまま使用し、[ **次へ**] をクリックします。

7.  [ **コマンドの実行** ] ページで、タスクの状態が [ **完了**] と表示されたら、[ **完了**] をクリックします。

8.  [ **手順 2: Lync Server コンポーネントのセットアップまたは削除**] の横にある [ **実行**] をクリックし、[ **次へ**] をクリックします。

9.  [ **コマンドの実行** ] ページで、タスクの状態が [ **完了**] と表示されたら、[ **完了**] をクリックします。

10. [ **手順 3: 証明書の要求、インストール、または割り当て**] の横にある [ **実行**] をクリックします。 画面に表示される指示に従って、既定の設定をそのまま適用します。 仲介サーバーは1つの証明書を必要とするため、 **手順 3** を2回実行します。1回は必要な証明書を発行し、もう一度割り当てるには。

11. 証明書が発行されて正しく割り当てられたら、[ **ステップ 4: サービスの開始**] の横にある [ **実行**] をクリックし、画面に表示される指示に従います。

12. **手順 4**が正常に完了したら、サーバーを再起動し、domainadmins グループのメンバーとしてサーバーにログオンします。

13. Lync Server コントロールパネルを実行しているコンピューターで、[Lync Server コントロールパネル] の [ **トポロジ** ] ページで、仲介サーバーのサービスの状態が緑のチェックマークとして表示されていることを確認します。 代わりに赤い X が表示される場合は、仲介サーバーを選択します。 [ **操作** ] メニューの [ **すべてのサービスの開始**] をクリックします。

仲介サーバープールに複数のコンピューターを追加した場合は、仲介サーバープール内の他のすべてのコンピューターで、この手順の手順を実行します。 他のコンピューターに対して仲介サーバー用のファイルをインストールする必要がない場合は、「configure [トランク In Lync server 2013](lync-server-2013-configuring-trunks.md) 」の手順に従って、この仲介サーバープール (またはサイト内のすべての仲介サーバー) とそのピアとの間のトランク接続の設定を構成します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

