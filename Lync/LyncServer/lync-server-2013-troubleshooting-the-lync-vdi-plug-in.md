---
title: 'Lync Server 2013: Lync VDI プラグインのトラブルシューティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Lync Server 2013 での Lync VDI プラグインのトラブルシューティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Thin クライアントに Lync VDI プラグインをインストールする際の問題のトラブルシューティング

シンクライアントに VDI プラグインをインストールするときに問題が発生した場合は、次の点を確認してください。

  - TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。

  - 書き込み保護がオフになっている。手順については、デバイス メーカーのドキュメントを参照してください。

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>ペアリングに関する問題のトラブルシューティング

VDI プラグインのペアリングに失敗した場合、右下のペアリングアイコンは、次のように赤い "X" として表示されます。

![成功したペアリングを示す LYNC VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "成功したペアリングを示す LYNC VDI アイコン")

次のような原因が考えられます。問題が発生した場合は、次のことを行ってください。

  - **ユーザーがサインインの際に入力した資格情報が正しくない。**
    
    ユーザーは、Lync からサインアウトし、正しい資格情報を使用してもう一度サインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。

  - **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。
    
    1.  タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
    2.  [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
    3.  各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。
    
    4.  新しいリモート デスクトップ セッションを起動して、もう一度接続してみます。

  - **必要なファイルが適切にインストールされていない。**
    
    プラグインをローカルコンピューターにインストールした後、C:\\Program Files\\Microsoft Office\\Office15 (または適切なドライブ文字) の下に次のファイルが表示されます。
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    VDI ペアリングで問題が発生した場合は、これらのファイルがローカルコンピューターに存在することを確認してください。

  - **Lync クライアントがローカルコンピューターで実行されている。**
    
    Lync VDI プラグインを使用するには、Lync クライアントがローカルコンピューターで実行されていない必要があります。そうでないと、ペアリングは失敗します。 ベストプラクティスとして、ユーザーはローカルコンピューターに Lync クライアントをインストールしないようにする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

