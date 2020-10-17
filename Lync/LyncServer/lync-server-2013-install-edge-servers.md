---
title: 'Lync Server 2013: エッジサーバーのインストール'
description: 'Lync Server 2013: エッジサーバーをインストールします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e699a7f41b0ee554bc85fb2d9a72a2d9a42870cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559583"
---
# <a name="install-edge-servers-for-lync-server-2013"></a>Lync Server 2013 のエッジサーバーのインストール

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

[Lync server 展開ウィザード] を使用して、エッジサーバーに Lync Server 2013 をインストールします。 各エッジ サーバーで展開ウィザードを実行することにより、エッジ サーバーのセットアップに必要なタスクの大部分を完了できます。 エッジサーバーに Lync Server 2013 を展開するには、既にトポロジビルダーを実行している必要があります。これにより、エッジサーバートポロジを定義して発行し、エッジサーバーから使用可能なメディアにエクスポートする必要があります。 詳細については、「 [Lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md) 」および「 [lync server 2013 トポロジをエクスポートして、エッジインストール用の外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。

展開ウィザードを使用して各エッジサーバーをインストールし、必要な証明書をインストールして割り当て、必要なサービスを開始するには、「 [Lync server 2013 2013 での外部ユーザーアクセスのサポートの構成](lync-server-2013-configuring-support-for-external-user-access.md)」に記載されている情報を[Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md)使用して設定を完了します。この情報を使用して、セットアップを検証します (サーバーとクライアントの

<div>

## <a name="to-install-an-edge-server"></a>エッジ サーバーをインストールするには

1.  Administrators グループのメンバーとして、または同等の権限およびアクセス権を有するアカウントとして、エッジ サーバーをインストールするコンピューターにログオンします。

2.  トポロジビルダーを使用して作成したトポロジ構成ファイルがエッジサーバーで使用できることを確認します (たとえば、トポロジ構成ファイルをコピーした USB ドライブにアクセスするか、またはファイルをコピーしたネットワーク共有へのアクセスを確認します)。

3.  展開ウィザードを開始します。
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ (再頒布可能) をインストール必要があるというメッセージが表示されたら、[<STRONG>はい</STRONG>] をクリックします。 次のダイアログ ボックスで、既定の [<STRONG>インストール先</STRONG>] をそのまま使用するか、または [<STRONG>参照</STRONG>] をクリックして別のロケーションを選択し、[<STRONG>インストール</STRONG>] をクリックします。 次のダイアログ ボックスで、[<STRONG>使用許諾契約書に同意します</STRONG>] チェック ボックスをオンにし、[<STRONG>OK</STRONG>] をクリックします。

    
    </div>

4.  展開ウィザードで、[**Lync Server システムのインストールまたは更新**] をクリックします。

5.  ウィザードが展開状態を判別した後、[**手順 1: ローカル構成ストアのインストール**] で [**実行**] をクリックし、次の手順に従います。
    
      - [**中央管理ストアのローカル レプリカの構成**] ダイアログ ボックスで、[**ファイルからインポートする (エッジ サーバーで推奨)**] をクリックします。エクスポートしたトポロジ構成ファイルのロケーションに進み、.zip ファイルを選択し、[**開く**] をクリックします。そして、[**次へ**] をクリックします。
    
      - 展開ウィザードが構成ファイルから構成情報を読み取り、ローカル コンピューターへ XML 構成ファイルを書き込みます。
    
      - [**コマンドの実行**] プロセスが完了した後、[**終了**] をクリックします。

6.  展開ウィザードで、[ **ステップ 2: Lync Server コンポーネントのセットアップまたは削除** ] をクリックして、ローカルコンピューターに格納されている XML 構成ファイルに指定されている lync server 2013 エッジコンポーネントをインストールします。

7.  インストールが完了したら、「 [Set Up Edge certificates For Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) 」の情報を使用して、サービスを開始する前に必要な証明書をインストールして割り当てます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

