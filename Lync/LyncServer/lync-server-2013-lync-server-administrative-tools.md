---
title: 'Lync Server 2013: Lync Server 管理ツール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a34561e9880870b53cd8f7aaad2fe13cfe33c8d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

このトピックでは、Lync Server 2013 の管理ツールについて説明します。

各 Lync Server サーバーには、既定で管理ツールがインストールされています。 さらに、専用の管理コンソールなど、他のコンピューターにも管理ツールをインストールできます。 管理ツールをインストールする手順については、「 [Lync Server 2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。 管理タスクを実行するためのツールを開く手順については、「 [Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

Lync Server 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティングシステム、ソフトウェア、および管理者の権限の要件を確認してください。 インフラストラクチャの要件の詳細については、「 [Lync Server 2013 での管理ツールインフラストラクチャの要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。 Lync Server 管理ツールをインストールするためのオペレーティングシステムとソフトウェアの要件の詳細については、「 [lync server 2013 のサーバーとツールのオペレーティングシステムサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「 [lync server 2013 のその他のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、「lync [server 2013 でのサーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。 ツールをインストールして使用するために必要なユーザー権限とアクセス許可については、「 [Lync Server 2013 のセットアップと管理に必要な管理者権限とアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」を参照してください。

管理ツールは次の要素で構成されています。

  - **Lync server 展開ウィザード**   は、lync server を展開し、すべての管理ツールをインストールするために使用されます。

  - **Lync Server Topology Builder**   は、展開でコンポーネントを定義するために使用されます。

  - **Lync Server コントロールパネル**   web ベースのインターフェイスを使用して展開を継続的に管理するために使用します。

  - **Lync Server 管理シェル**   は、コマンドラインを使用して展開を継続的に管理するために使用されます。

  - **Lync Server ログツール**   を使用して、展開の問題のトラブルシューティングを行うことができます。

  - **集中ログサービス**   1 台のコンピューター、プール、サイト、またはグローバルからログとトレースファイルを収集します。 プロバイダー、フラグ、トレースレベルを含むシナリオを選択して定義します。 ログは、テキストベースのツールや Snooper などのツールを使って収集、集計、表示されます。

主にトポロジビルダーと Lync Server コントロールパネルを使用して、展開を管理することができます。

<div>

## <a name="deployment-wizard"></a>展開ウィザード

Lync server をまだインストールしていないコンピューターにすべての管理ツールをインストールするには、インストールメディアに含まれている Lync Server 展開ウィザードを使用する必要があります。 管理ツールのインストールプロセスでは、Lync Server 展開ウィザードが他のツールと共にインストールされているため、後で追加のコンポーネント用のファイルをインストールしたり、必要のないコンポーネントのファイルを削除したりすることができます。pc.

Lync server のインストールメディアから初めて Lync Server Deployment ウィザードを実行する方法の詳細については、「 [Lync server 2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。

</div>

<div>

## <a name="topology-builder"></a>トポロジ ビルダー

トポロジビルダーを使用して実行できる展開タスクの詳細については、各サーバーの役割の展開ドキュメントを参照してください。

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server コントロール パネル

Lync Server 2013 コントロールパネルを使用すると、Lync Server 2013 の管理と保守に必要な管理タスクのほとんどを実行できます。 Lync Server コントロールパネルには、組織内のユーザー、クライアント、およびデバイスに加えて、Lync Server を実行しているサーバーの構成を管理するグラフィカルユーザーインターフェイス (GUI) が用意されています。 Lync server 管理シェルは、lync server のコントロールパネルを使用して、Lync Server の構成を実行するための基盤となるメカニズムとして使用します。

Lync Server コントロールパネルは、Lync Server のすべてのフロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。 このリリースでは、リモートでエッジサーバーを管理します。 Lync server コントロールパネルは、Lync Server を一元管理する管理コンソールなどの、別のコンピューターにインストールすることもできます。 詳細については、「 [Lync Server 2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server コントロールパネルを使用して設定を構成するには、CsAdministrator の役割に割り当てられているアカウントを使用してログインしている必要があります。 Lync Server 2013 で利用できる定義済みの管理者ロールの詳細については、「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync server 2013 でのロールベースのアクセス制御の計画</A>」を参照してください。</P>
> <LI>
> <P>Lync Server コントロールパネルを使用して設定を構成するには、最低でも 1024 x 768 の画面解像度を備えたコンピューターを使用する必要があります。</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server 管理シェル

Lync server の管理シェルでは、管理と管理のための新しい方法が用意されています。 Lync Server Management Shell は、Windows PowerShell コマンドラインインターフェイスに基づいて構築された強力な管理インターフェイスであり、Lync Server 固有の一連の包括的なコマンドレットが含まれています。 Lync Server 管理シェルを使用すると、豊富な構成とオートメーションコントロールのセットを入手できます。 トポロジビルダーと Lync Server コントロールパネルはどちらも、Lync Server の管理をサポートするために、これらのコマンドレットのサブセットを実装しています。 Lync Server 管理シェルには、すべての Lync Server 管理タスク用のコマンドレットが含まれています。また、コマンドレットを個別に使用して展開を管理することもできます。 詳細については、「 [Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)ドキュメント」または各コマンドレットのコマンドラインヘルプを参照してください。

</div>

<div>

## <a name="logging-tool"></a>ログツール

Lync Server ログツールを使って、製品の実行中に製品からログとトレース情報をキャプチャすることで、トラブルシューティングを容易に行うことができます。 このツールを使用して、任意の Lync Server サーバーの役割でデバッグセッションを実行できます。 ログツールの詳細については、TechNet ライブラリの Lync Server 2010 Logging Tool のマニュアルを[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)参照してください。

<div>


> [!IMPORTANT]  
> すべての状況で Lync Server ログツールを介してすべてのログ収集を行う場合は、一元ログサービスをお勧めします。 Lync Server ログツールは引き続き動作しますが、集中化されたログサービスが既に実行されている場合は、ほとんどの場合、影響を受ける可能性があります。 一元管理サービスまたは Lync Server ログツールのみを使用する必要がありますが、同時に両方を使用することはできません。 一元管理サービスの詳細と、それを排他的に使用する理由については、「 <A href="lync-server-2013-using-the-centralized-logging-service.md">Lync Server 2013 での集中ログサービスの使用</A>」を参照してください。



</div>

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での管理ツールインフラストラクチャの要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 の管理ツールのソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)

  - [Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Lync Server 2013 でトポロジを公開する場合の要件](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 コントロールパネルのトラブルシューティング](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Lync Server 2013 での一元管理ログサービスの使用](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

