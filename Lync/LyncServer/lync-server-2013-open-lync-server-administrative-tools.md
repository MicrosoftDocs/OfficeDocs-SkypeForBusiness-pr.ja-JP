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
ms.openlocfilehash: 172d448b3967782226335a5a3b9a4066514b7a9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツールを開く

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-28_

このトピックの手順を使用して、Lync Server 2013 トポロジの展開、構成、またはトラブルシューティングを行うための管理ツールを開くことができます。

  - 展開ウィザード

  - トポロジ ビルダー

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>展開ウィザード

Lync Server 2013 コンポーネントファイルを追加または削除するために、展開ウィザードをローカルで開始するには、次の手順を使用します。

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Lync Server 2013 展開ウィザードを起動するには

1.  Lync Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  [**スタート**]、[**すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server 展開ウィザード**] の順にクリックします。

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>トポロジ ビルダー

次の手順を使用して、トポロジビルダーを開き、Lync Server 2013 トポロジに展開するサーバーを定義します。

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Lync Server 2013 トポロジビルダーを開いてトポロジを設計するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、サーバーに Lync Server 2013 をインストールするために必要なトポロジを読み取り、公開、または有効にするには、Domain Admins グループおよび RTCUniv のメンバーであるアカウントを使用する必要があります。ersalServerAdmins グループで、アーカイブファイルストアに対して使用するファイル共有に対するフルコントロールのアクセス許可 (読み取り、書き込み、および変更) を持ち、トポロジビルダーが必要な随意アクセス制御リスト (Dacl) を構成できるようにします。または、それと同等のユーザー権限を持つアカウント。

    
    </div>

2.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 コントロール パネル

次のいずれかの手順を使用して、Lync Server 2013 コントロールパネルを開いて、環境内のサーバー、ユーザー、クライアント、デバイスの構成を管理します。

<div>


> [!NOTE]  
> CsAdministrator の役割に割り当てられているユーザーアカウントを使用して、Lync Server 2013 コントロールパネルのすべてのタスクを実行できます。 他の役割を使用して Lync Server 2013 コントロールパネルにログオンすると、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して Lync Server 2013 コントロールパネルのアーカイブを管理できます。 役割の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。 特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>組織のファイアウォールの内側にある任意のコンピューターから Lync Server 2013 コントロールパネルを開くには

1.  CsAdministrator の役割、またはタスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割に割り当てられているユーザーアカウントから、最小画面解像度 1024 x 768 を使用して、内部展開の任意のコンピューターにログオンします。
    
    <div>
    

    > [!IMPORTANT]  
    > 管理シンプルな uniform resource locator (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネットブラウザーから Lync Server 2013 コントロールパネルにアクセスできます。 管理の簡単な URL の構成の詳細については、「展開」のドキュメントの「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-simple-urls.md">Lync server 2013 での簡単な url の計画</A>」および「 <A href="lync-server-2013-edit-or-configure-simple-urls.md">lync server 2013 での簡易 url の編集または構成</A>」を参照してください。

    
    </div>

2.  ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Lync server 2013 を実行しているコンピューターで Lync Server 2013 コントロールパネルを開くには

1.  CsAdministrator の役割のメンバーである、またはタスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割のメンバーであるユーザーアカウントから、Lync Server 2013 をインストールしたコンピューターにログオンするか、少なくとも Lync Server 2013 admin をインストールします。ive ツール。 設定を構成するには、コンピューターの最小画面解像度を 1024 x 768 にする必要があります。

2.  Lync Server 2013 コントロールパネルを開きます。 [**スタート**]、[**すべてのプログラム**]、[**管理ツール**] の順にポイントし、[ **Microsoft lync server 2013**] をポイントして、[ **lync server 2013 コントロールパネル**] をクリックします。

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理シェル

次の手順を使用して、Lync Server 2013 管理シェルを開き、コマンドラインを使用して環境内のサーバー、ユーザー、クライアント、およびデバイスを管理します。

<div>


> [!NOTE]  
> CsAdministrator の役割に割り当てられているユーザーアカウントを使用して、Lync Server 2013 管理シェルで任意のタスクを実行できます。 特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。 たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。 役割の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。 特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。<BR>コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを開くには

  - Lync Server 2013 管理シェルではなく、Windows PowerShell ウィンドウを開くと、既定で Lync Server 2013 コマンドレットを実行することはできません。 Windows PowerShell で Lync Server 2013 コマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次のように入力します。
    
    `Import-Module Lync`

  - Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理ツールのインストール](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

