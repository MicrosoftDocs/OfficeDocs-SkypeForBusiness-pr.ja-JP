---
title: 'Lync Server 2013: Lync Server 管理ツールのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8805c82c26eb97da8537b33cda8346f5942de1c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツールのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

このトピックでは、Lync Server 2013 を展開および管理するために使用する必要がある管理ツールをインストールする方法について説明します。 管理ツールは、Lync Server 2013 を実行している各サーバーに既定でインストールされます。 また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 Active Directory ドメインサービスの準備手順が既に完了していることを確認してから、作成する Lync Server 2013 の展開と同じドメインまたはフォレストにあるコンピューターに管理ツールをインストールすることを強くお勧めします。complete。これにより、後でそのコンピューター上の管理ツールを使用して、トポロジを公開することができます。

Lync Server 2013 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティングシステム、ソフトウェア、および管理者の権限要件を確認してください。 インフラストラクチャ要件の詳細については、「 [Lync Server 2013 の管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。 Lync Server 2013 管理ツールをインストールするためのオペレーティングシステムとソフトウェアの要件の詳細については、「lync server [2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「lync [server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、および「 [lync server 2013 の追加のサーバーサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。 ツールのインストールと使用に必要なユーザー権限とアクセス許可の詳細については、「 [Lync Server 2013 のセットアップと管理に必要な管理者権限とアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」を参照してください。

<div>


> [!IMPORTANT]  
> 組織でインターネット インフォメーション サービス (IIS) およびすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、[セットアップ] ダイアログ ボックスで Lync Server ファイルのインストール先パスを変更できます。 このパス (OCSCore を含む) にセットアップファイルをインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツールをインストールするには

1.  管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。Windows Vista または Windows 7 オペレーティング システムの標準ユーザーとしてログオンしており、ユーザー アカウント制御 (UAC) が有効になっている場合は、ローカル管理者または同等のドメイン ユーザーの名前とパスワードの入力を求められます。

2.  コンピューターでインストールメディアを見つけ、[setup \\\\amd64\\setup.exe] をダブルクリックします。

3.  Microsoft Visual C++ 2008 (再頒布可能) のインストールを指示されたら、[**はい**] をクリックします。

4.  [ **Microsoft Lync Server 2013 のインストール先**] ページで、[ **OK**] をクリックします。 ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。
    
    <div>
    

    > [!IMPORTANT]  
    > インターネットインフォメーションサービス (IIS) とすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、[セットアップ] ダイアログボックスで Lync Server 2013 ファイルのインストール場所のパスを変更できます。 このパス (OCSCore を含む) にセットアップファイルをインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。

    
    </div>

5.  [**使用許諾契約書**] ページでライセンス条項を確認し、[**同意する**] をクリックしてから [**OK**] をクリックします。続行するにはこのステップが必要です。

6.  [ **Microsoft Lync Server 2013-展開ウィザード**] ページで、[**管理者ツールのインストール**] をクリックします。

7.  インストールが正常に完了したら、[**終了**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

