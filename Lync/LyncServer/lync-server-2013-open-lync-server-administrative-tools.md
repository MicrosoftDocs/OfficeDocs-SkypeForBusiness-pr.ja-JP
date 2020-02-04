---
title: 'Lync Server 2013: Lync Server 管理ツールを開く'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツールを開く

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-28_

このトピックの手順を使用して、Lync Server 2013 トポロジの展開、構成、トラブルシューティングを行うための管理ツールを開くことができます。

  - 展開ウィザード

  - トポロジ ビルダー

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>展開ウィザード

Lync Server 2013 コンポーネントファイルを追加または削除するために展開ウィザードをローカルで開始するには、次の手順を使用します。

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Lync Server 2013 展開ウィザードを起動するには

1.  Lync Server 展開ウィザードがドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。

2.  [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **Microsoft Lync server 2013**] をクリックして、[ **Lync server Deployment Wizard**] をクリックします。

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>トポロジ ビルダー

次の手順を使用して、[トポロジビルダー] を開いて、Lync Server 2013 トポロジに展開するサーバーを定義します。

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Lync Server 2013 トポロジビルダーを開いてトポロジを設計するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジは、ローカルユーザーグループのメンバーであるアカウントを使用して定義できますが、サーバーに Lync Server 2013 をインストールするために必要なトポロジを読み取り、公開、または有効にするには、ドメイン管理者グループと RTCUniv のメンバーであるアカウントを使用する必要があります。ersalServerAdmins グループで、アーカイブファイルストアで使用するファイル共有に対するフルコントロールのアクセス許可 (つまり読み取り、書き込み、変更) が含まれているため、トポロジビルダーは必要な随意アクセス制御リスト (Dacl) を構成できます。または、同等のユーザー権限を持つアカウント。

    
    </div>

2.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 コントロール パネル

次のいずれかの手順を使用して、Lync Server 2013 コントロールパネルを開き、環境内のサーバー、ユーザー、クライアント、デバイスの構成を管理します。

<div>


> [!NOTE]  
> CsAdministrator ロールに割り当てられているユーザーアカウントを使用して、Lync Server 2013 コントロールパネルで任意のタスクを実行することができます。 他の役割を使用して、Lync Server 2013 コントロールパネルにログオンして、実行する必要があるタスクに応じて、特定の管理タスクを実行することができます。 たとえば、CSArchivingAdministrator を使用して、Lync Server 2013 コントロールパネルのアーカイブを管理することができます。 ロールの詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。 特定のタスクを実行するために使用できる役割の詳細については、そのタスクに関するドキュメントを参照してください。



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>組織のファイアウォール内の任意のコンピューターから Lync Server 2013 コントロールパネルを開くには

1.  CsAdministrator の役割またはその他の役割に割り当てられているユーザーアカウントで、タスクを実行するための適切なユーザー権限と権限を持っている場合は、最小画面解像度 1024 x 768 を使用して、内部展開内の任意のコンピューターにログオンします。
    
    <div>
    

    > [!IMPORTANT]  
    > 管理のシンプルな uniform resource locator (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネットブラウザーから Lync Server 2013 コントロールパネルにアクセスできます。 管理のシンプルな URL の構成の詳細については、「計画ドキュメントの「 <A href="lync-server-2013-planning-for-simple-urls.md">Lync server 2013 での単純な url の計画</A>」および「展開ドキュメントの<A href="lync-server-2013-edit-or-configure-simple-urls.md">lync server 2013 での単純な url の編集または構成</A>」を参照してください。

    
    </div>

2.  ブラウザーウィンドウを開き、組織に構成されている管理 URL を入力します。

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Lync server 2013 コントロールパネルを Lync Server 2013 を実行しているコンピューターで開くには

1.  CsAdministrator の役割のメンバーであるユーザーアカウント、またはタスクを実行するための適切なユーザー権限と権限を持つユーザーアカウントの場合は、Lync Server 2013 をインストールしたコンピューターにログオンするか、少なくとも Lync Server 2013 admin でたツール。 設定を構成するには、コンピューターの画面解像度が 1024 x 768 以上である必要があります。

2.  Lync Server 2013 コントロールパネルを起動します。 [**スタート**]、[**すべてのプログラム**]、[**管理ツール**]、[ **Microsoft lync server 2013**] の順にポイントして、[ **lync server 2013 コントロールパネル**] をクリックします。

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理シェル

次の手順を使用して、Lync Server 2013 管理シェルを開き、コマンドラインを使用して、環境内のサーバー、ユーザー、クライアント、デバイスを管理します。

<div>


> [!NOTE]  
> CsAdministrator ロールに割り当てられているユーザーアカウントを使用して、Lync Server 2013 管理シェルで任意のタスクを実行することができます。 他の役割を使用してログオンし、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して、アーカイブ管理に関連するコマンドレットを実行することができます。 ロールの詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。 特定のコマンドレットを実行するために使用できる役割の詳細については、コマンドレットのドキュメントを参照してください。<BR>また、コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins グループのユーザーアカウントを使用して、特定のコマンドレットを実行することもできます。



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを開くには

  - Lync Server 2013 管理シェルではなく、Windows PowerShell ウィンドウを開いた場合、既定では Lync Server 2013 コマンドレットを実行することはできません。 Windows PowerShell 内から Lync Server 2013 コマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次を入力します。
    
    `Import-Module Lync`

  - Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

