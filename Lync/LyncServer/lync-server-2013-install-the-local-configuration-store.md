---
title: 'Lync Server 2013: ローカル構成ストアのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Lync Server 2013 でのローカル構成ストアのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-27_

次の手順を実行する前に、ローカル管理者と RTCUniversalReadOnlyAdmin グループの両方のドメインユーザーアカウントでサーバーにログオンしていることを確認してください。

Lync Server 展開ウィザードで何かを実行できるようにするには、サーバー上にローカル構成ストアが存在している必要があります。 ローカル構成ストアは、SQL Server Express のローカルインストールの後に作成される、中央管理ストアの読み取り専用コピーです。 サーバーの全体管理ストアは、Standard Edition server または SQL Server Express ベースのデータベースにインストールされている既存の SQL Server データベースに追加されます。

<div>


> [!IMPORTANT]  
> このサーバーで Lync Server 2013 セットアップを実行していない場合は、Lync Server 2013 をインストールするためのドライブとパスを入力するように求められます。 これにより、必要に応じて、システムドライブ以外のドライブにインストールすることができます。 [セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを、使用可能な新しいドライブに変更することができます。 このパス (OCSCore など) にセットアップファイルをインストールすると、Lync Server の他の2013ファイルも一緒に展開されます。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>ローカル構成ストアをインストールするには

1.  インストールメディアから\\、setup\\amd64\\Setup.exe を参照し、[ **OK]** をクリックします。

2.  Microsoft Visual C++ 2012 の再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。

3.  **Lync Server 2013 のインストール場所**のページで、[ **OK**] をクリックします。

4.  [**エンドユーザーライセンス契約**] ページで、ライセンス条項を確認し、[使用許諾**契約書の条項に同意**します] を選択してから、[ **OK** ] をクリックして続行できるようにします。

5.  展開ウィザードのページで、[ **Lync Server System のインストールまたは更新**] をクリックします。

6.  **Lync Server 2013**ページで、[ステップ 2 **: ローカル構成ストアをインストール**します] の横にある [**実行**] をクリックします。

7.  [**ローカル構成ストアのインストール**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。

8.  ローカルサーバー構成のインストールが完了したら、[**完了**] をクリックする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

