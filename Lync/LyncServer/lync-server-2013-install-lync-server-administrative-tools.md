---
title: 'Lync Server 2013: Lync Server 管理ツールをインストールする'
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
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツールをインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

このトピックでは、Lync Server 2013 を展開して管理するために必要な管理ツールをインストールする方法について説明します。 管理ツールは、Lync Server 2013 を実行している各サーバーに既定でインストールされます。 さらに、専用の管理コンソールなど、他のコンピューターにも管理ツールをインストールできます。 Active Directory ドメインサービスの準備手順が既に行われていることを確認して、作成中の Lync Server 2013 展開と同じドメインまたはフォレストにあるコンピューターに管理ツールをインストールすることを強くお勧めします。[完了] を選択すると、後でそのコンピューターの管理ツールを使用してトポロジを公開できます。

Lync Server 2013 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティングシステム、ソフトウェア、および管理者の権限の要件を確認してください。 インフラストラクチャの要件の詳細については、「 [Lync Server 2013 での管理ツールインフラストラクチャの要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。 Lync Server 2013 管理ツールをインストールするためのオペレーティングシステムとソフトウェアの要件の詳細については、「lync server [2013 のサーバーとツールのオペレーティングシステムサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「 [lync server 2013 のその他のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、「 [Lync server 2013 のその他のサーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。 ツールをインストールして使用するために必要なユーザー権限と権限の詳細については、「 [Lync Server 2013 のセットアップと管理に必要な管理者権限とアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」を参照してください。

<div>


> [!IMPORTANT]  
> 組織でインターネットインフォメーションサービス (IIS)、およびシステムドライブ以外のドライブ上のすべての Web サービスを検索する必要がある場合は、[セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを変更することができます。 このパス (OCSCore など) にセットアップファイルをインストールすると、Lync Server の他の2013ファイルもこのドライブに展開されます。



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツールをインストールするには

1.  管理ツールをインストールするコンピューターにローカルの管理者 (最小要件) としてログオンします。 Windows Vista または Windows 7 オペレーティングシステムで標準ユーザーとしてログオンしていて、ユーザーアカウント制御 (UAC) が有効になっている場合は、ローカルの管理者またはドメインの同等のユーザー名とパスワードを入力するように求められます。

2.  使用しているコンピューター上でインストールメディアを探し、setup \\\\amd64\\setup.exe をダブルクリックします。

3.  Microsoft Visual C++ 2008 の配布可能な製品をインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。

4.  **Microsoft Lync Server 2013 のインストール場所**のページで、[ **OK]** をクリックします。 ファイルを別の場所にインストールする必要がある場合は、このパスを別の場所またはドライブに変更します。
    
    <div>
    

    > [!IMPORTANT]  
    > 組織でインターネットインフォメーションサービス (IIS)、およびシステムドライブ以外のドライブ上のすべての Web サービスを検索する必要がある場合は、セットアップダイアログボックスで Lync Server 2013 ファイルのインストール場所のパスを変更することができます。 このパス (OCSCore など) にセットアップファイルをインストールした場合、Lync Server の他の2013ファイルもこのドライブに展開されます。

    
    </div>

5.  [**エンドユーザーライセンス契約**] ページで、ライセンス条項を確認し、[**同意**する] をクリックして、[ **OK**] をクリックします。 続行するには、この手順が必要です。

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

