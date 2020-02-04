---
title: 'Lync Server 2013: Standard Edition サーバー データベースのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Lync Server 2013 の Standard Edition サーバー データベースのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

インフラストラクチャ内で、標準エディションのサーバーをインフラストラクチャ内の唯一のサーバーとして設定します。これは、**展開ウィザード**で最初のサーバーを設定することを目的としています。

<div>

## <a name="to-install-a-standard-edition-server"></a>Standard Edition サーバーをインストールするには

1.  Standard Edition server をインストールしようとしているサーバーに、ローカル管理者または同等のドメインとしてログオンします。

2.  Active Directory ドメインサービスの準備ができていない場合は、最初にこれらの手順を実行します。 詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。

3.  Lync Server 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。

4.  [**単一標準エディションサーバーの準備**] ページで、[**次へ**] をクリックします。

5.  [**コマンドの実行**] ページで、SQL Server 2012 Express が中央管理ストアとしてインストールされています。 必要なファイアウォールルールが作成されます。 データベースと必須ソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 最初のインストールでは、コマンド出力の概要画面に表示される更新プログラムがないと、時間がかかる場合があります。 これは、SQL Server Express がインストールされているためです。 データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。

    
    </div>

6.  [Lync Server 展開ウィザード] ページで、[管理ツール] をまだインストールしていない場合は、[**トポロジビルダーのインストール**] をクリックします。 詳細については、「 [Lync Server 2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。

7.  [Active Directory の準備] の横に緑色のチェックマークが表示されていることを確認します。 "最初の Standard Edition サーバーの準備" と "トポロジビルダーのインストール" を確認してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

