---
title: 'Lync Server 2013: Lync VDI プラグインのトラブルシューティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe652a2a378759584b8d855cdcdc7790b622ad02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518964"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Lync Server 2013 での Lync VDI プラグインのトラブルシューティング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Lync VDI プラグインをシンクライアントにインストールする際の問題のトラブルシューティング

シン クライアントへの VDI プラグインのインストールに関して問題がある場合は、次のことを確認してください。

  - TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。

  - 書き込み保護がオフになっている。手順については、デバイス メーカーのドキュメントを参照してください。

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>ペアリングに関する問題のトラブルシューティング

VDI プラグインのペアリングに失敗すると、右下のペアリング アイコンが赤色の "X" で表示されます。

![ペアリングが成功したことを示す Lync VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "ペアリングが成功したことを示す Lync VDI アイコン")

失敗の原因の可能性と対策を、以下に示します。

  - **ユーザーがサインインの際に入力した資格情報が正しくない。**
    
    ユーザーは、Lync からサインアウトし、正しい資格情報を使用して再度サインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。

  - **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を実行する必要があります。
    
    1.  タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
    2.  [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
    3.  各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。
    
    4.  新しいリモート デスクトップ セッションを起動して、再び接続を試みます。

  - **必要なファイルが適切にインストールされていない。**
    
    プラグインがローカルコンピューターにインストールされた後、C: \\ Program files \\ Microsoft Office \\ Office15 (または適切なドライブ文字) の下に次のファイルが表示されます。
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    VDI ペアリングに何か問題がある場合は、これらのファイルがローカル コンピューター上に存在することを確認してください。

  - **Lync クライアントは、ローカルコンピューター上で実行されています。**
    
    Lync VDI プラグインを使用するには、Lync クライアントがローカルコンピューター上で実行されていてはなりません。そうでないと、ペアリングは失敗します。 ベストプラクティスとして、ユーザーは、Lync クライアントをローカルコンピューターにインストールしないようにしてください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

