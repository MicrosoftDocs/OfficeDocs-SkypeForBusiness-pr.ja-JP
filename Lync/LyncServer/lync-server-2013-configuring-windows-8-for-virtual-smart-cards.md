---
title: 'Lync Server 2013: 仮想スマートカード用の Windows 8 の構成'
description: 'Lync Server 2013: 仮想スマートカード用の Windows 8 の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542163"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Lync Server 2013 で仮想スマートカードを使用するための Windows 8 の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-03_

2要素認証とスマートカードテクノロジを展開する際に考慮する要因の1つは、実装コストです。 Windows 8 には新しいセキュリティ機能がいくつか用意されており、最も興味深い新機能の1つは仮想スマートカードのサポートです。

仕様バージョン1.2 を満たすトラステッドプラットフォームモジュール (TPM) チップを備えたコンピューターの場合、組織は、ハードウェアに追加の投資を行わずにスマートカードログオンの利点を得ることができます。 詳細については、「Windows 8 での仮想スマートカードの使用」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) 。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>仮想スマートカード用に Windows 8 を構成するには

1.  Lync が有効なユーザーの資格情報を使用して、Windows 8 コンピューターにログインします。

2.  Windows 8 のスタート画面で、カーソルを画面の右下隅に移動します。

3.  **検索**オプションを選択し、**コマンドプロンプト**を検索します。

4.  [ **コマンドプロンプト**] を右クリックし、[ **管理者として実行**] を選択します。

5.  次のコマンドを実行して、トラステッドプラットフォームモジュール (TPM) 管理コンソールを開きます。
    
        Tpm.msc

6.  TPM 管理コンソールから、TPM 仕様バージョンが少なくとも1.2 であることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 互換性のある信頼できるプラットフォームモジュール (TPM) が見つからないことを示すダイアログボックスが表示された場合は、コンピューターに互換性のある TPM モジュールがあり、システム BIOS で有効になっていることを確認してください。

    
    </div>

7.  TPM 管理コンソールを閉じる

8.  コマンドプロンプトで、次のコマンドを使用して、新しい仮想スマートカードを作成します。
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 仮想スマートカードを作成するときにカスタムの PIN 値を指定するには、代わりに [/pin プロンプト] を使用します。

    
    </div>

9.  コマンドプロンプトで、次のコマンドを実行して、コンピューターの管理コンソールを開きます。
    
        CompMgmt.msc

10. [コンピューターの管理] コンソールで、[ **デバイス管理**] を選択します。

11. [ **スマートカード読み取り装置**] を展開します。

12. 新しい仮想スマートカードリーダーが正常に作成されたことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

