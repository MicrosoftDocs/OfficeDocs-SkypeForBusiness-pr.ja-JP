---
title: 'Lync Server 2013: 仮想スマートカード用の Windows 8 の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Lync Server 2013 で仮想スマートカードを使用するための Windows 8 の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-03_

2 要素認証とスマート カード テクノロジを展開する場合に考慮する必要がある要素の 1 つは、実装コストです。 Windows 8 には新しいセキュリティ機能が数多く用意されています。また、最も重要な新機能の1つは仮想スマートカードをサポートしています。

バージョン 1.2 仕様を満たす Trusted Platform Module (TPM) チップを搭載したコンピューターでは、ハードウェアの追加費用をかけずにスマート カード ログオンを活用できるようになりました。 詳細については、「Windows 8 での仮想スマート[http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)カードの使用」を参照してください。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Windows 8 を仮想スマート カード用に構成するには

1.  Lync 対応ユーザーの資格情報を使用して、Windows 8 コンピューターにログインします。

2.  Windows 8 のスタート画面で、画面の右下隅にカーソルを移動します。

3.  [**検索**] オプションを選択し、「**Command Prompt**」を検索します。

4.  [**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

5.  次のコマンドを実行して、Trusted Platform Module (TPM) 管理コンソールを開きます。
    
        Tpm.msc

6.  TPM 管理コンソールで、TPM 仕様バージョンが 1.2 以上であることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 相互運用性のある Trust Platform Module (TPM) が見つからないことを示すダイアログが表示された場合は、相互運用性のある TPM モジュールがコンピューターにインストールされていること、およびシステム BIOS で有効になっていることを確認します。

    
    </div>

7.  TPM 管理コンソールを閉じる

8.  コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 仮想スマート カードを作成するときにカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。

    
    </div>

9.  コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。
    
        CompMgmt.msc

10. コンピューター管理コンソールで、[**デバイス管理**] をクリックします。

11. [**スマート カード リーダー**] を展開します。

12. 新しい仮想スマート カード リーダーが正しく作成されていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

