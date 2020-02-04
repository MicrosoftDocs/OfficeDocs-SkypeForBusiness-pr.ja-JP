---
title: 'Lync Server 2013: 仲介サーバー用のファイルをインストールする'
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
ms.openlocfilehash: c84d5fc2c863e0e56af275a4bee084652742eeac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 で仲介サーバー用のファイルをインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-06_

この手順を正常に完了するには、少なくともローカルの管理者または RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとして、サーバーにログオンしている必要があります。

このトピックの手順を使用して、Lync Server 2013 展開ウィザードを実行し、トポロジビルダーを使用してプールを定義して発行するときに、仲介サーバープールに追加したコンピューターに仲介サーバー用のファイルをインストールします。 ファイル仲介サーバーをインストールする場合は、仲介サーバープール内の各コンピューターに必要な証明書もインストールして割り当てます。

このサイトでは、フロントエンドプールまたは Standard Edition サーバーに併置されている仲介サーバーを既に展開している場合は、このトピックをスキップすることができます。代わりに、 [Lync server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)を続行します。

<div>


> [!NOTE]  
> このトピックでは、「 <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013 のトポロジビルダーでの仲介サーバーの定義</A>」の説明に従って、スタンドアロンの仲介サーバープールを既に定義して公開していることを前提とし、展開ドキュメントで<A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A>し、仲介サーバーのプール内のコンピューターが<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">lync server 2013 の</A><A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">セキュリティと構成の前提条件を満たしてLync Server 2013 での音声</A>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>スタンドアロンの仲介サーバー プールにファイルをインストールするには

1.  インストールメディアから\<[インストールメディア\>**\\のセットアップ\\amd64\\**] を右クリックし、[**管理者として実行**] をクリックします。

2.  [**インストール先**] ページで、[**OK**] をクリックします。

3.  [**使用許諾契約書**] ページで [**同意する**] をクリックし、[**OK**] をクリックします (操作を続行する必要があります)。

4.  **Lync server 2010 展開ウィザード**のページで、[ **lync Server System のインストールまたは更新**] をクリックします。

5.  [**ステップ 1: ローカル構成ストアのインストール**] の横の [**実行**] をクリックし、画面の指示に従います。

6.  [**中央管理ストアのローカル レプリカの構成**] ページで、既定の [**中央管理ストアから直接取得する**] を受け入れ、[**次へ**] をクリックします。

7.  [**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。

8.  **「手順 2: Lync サーバーコンポーネントをセットアップまたは削除**する」の横にある [**実行**] をクリックし、[**次へ**] をクリックします。

9.  [**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。

10. [**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。画面に表示される指示に従って、既定の設定を承諾します。仲介サーバーには証明書が 1 つ必要なため、[**ステップ 3**] を 2 回実行します。つまり、1 回目で必要な証明書を発行して、2 回目で割り当てを行います。

11. 証明書を発行し正しく割り当てたら、[**ステップ 4: サービスの開始**] の横の [**実行**] をクリックし、画面の指示に従います。

12. [**ステップ 4**] が正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。

13. Lync Server コントロールパネルを実行しているコンピューターで、仲介サーバーのサービスの状態が緑色のチェックマークとして表示される、Lync Server コントロールパネルの [**トポロジ**] ページを確認します。 代わりに赤い X が表示される場合は、仲介サーバーを選びます。 [**操作**] メニューの [**すべてのサービスを開始**] をクリックします。

複数のコンピューターを仲介サーバープールに追加した場合は、仲介サーバープール内の他のすべてのコンピューターで、この手順の手順を実行します。 他のコンピューターに対して仲介サーバー用のファイルをインストールする必要がない場合は、「 [Lync server 2013 で trunks を構成](lync-server-2013-configuring-trunks.md)する」の手順に従って、この仲介サーバープール (またはサイト内のすべての仲介サーバー) とピアの間のトランク接続の設定を構成します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

