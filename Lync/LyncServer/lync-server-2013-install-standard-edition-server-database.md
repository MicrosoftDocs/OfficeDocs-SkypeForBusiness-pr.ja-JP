---
title: 'Lync Server 2013: Standard Edition サーバーデータベースのインストール'
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
ms.openlocfilehash: 877a9b8519c6c0e8b0c3e4a92d190f5a55d8861e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Lync Server 2013 用の Standard Edition サーバーデータベースのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

Standard Edition サーバーをインフラストラクチャ内の唯一のサーバーとして設定します。これは、ユーザーのホームサーバーとは異なり、**展開ウィザード**では、最初のサーバーをセットアップするための選択があります。

<div>

## <a name="to-install-a-standard-edition-server"></a>Standard Edition サーバーをインストールするには

1.  Standard Edition サーバーをインストールするサーバーに、ローカル管理者またはドメインと同等のサーバーにログオンします。

2.  Active Directory ドメインサービスを準備していない場合は、最初にこれらの手順を実行します。 詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。

3.  Lync Server 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。

4.  [**単一の Standard Edition サーバーの準備**] ページで、[**次へ**] をクリックします。

5.  [**コマンドの実行**] ページで、SQL Server 2012 Express が中央管理ストアとしてインストールされます。 必要なファイアウォール規則が作成されます。 データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 最初のインストールには、コマンド出力の概要画面に表示される更新がないと、しばらく時間がかかる場合があります。 これは、SQL Server Express がインストールされているためです。 データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。

    
    </div>

6.  [Lync Server 展開ウィザード] ページで、以前に管理ツールをインストールしていない場合は、[**トポロジビルダーのインストール**] をクリックします。 詳細については、「 [Install Lync Server 2013 管理ツール](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。

7.  [Active Directory の準備]、[最初の Standard Edition サーバーの準備]、および [トポロジ ビルダーのインストール] の横に緑のチェック マークが付いていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

