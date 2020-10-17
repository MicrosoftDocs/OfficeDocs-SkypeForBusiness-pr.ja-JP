---
title: 負荷を実行するためのトポロジのプロビジョニング
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45b1c9d320ef35555e83bbd8851d77e00a452631
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509110"
---
# <a name="provisioning-the-topology-to-run-load"></a>負荷を実行するためのトポロジのプロビジョニング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-04_

<div>

既存の設定と Lync Server 2013 の構成によっては、環境を次のように変更する必要があります。

1.  Windows PowerShell 実行ポリシーを無制限に設定します。 実行ポリシーの設定を確認するには、Lync Server 管理シェルを開き、次のコマンドを実行します。

    ``` powershell
        Get-ExecutionPolicy
    ```        

    このコマンドで無制限の値が返されない場合は、次のコマンドを実行します。

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Lync Server 2013 を効果的に構成するには、次のことを行う必要があります。
    
      - Lync Server 2013 トポロジ (コンピューター名、サービスインスタンス、サイト名、ポリシーなど) について理解していること。
    
      - 応答グループのハントグループ (たとえば、SIP Uri) など、グループに作成された一部のユーザーを割り当てます。

3.  コマンドラインからスクリプトを実行するには、次のように使用します。

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  通常、このパッケージのスクリプトのいずれかが実行されると、スクリプトから得られたトレースは、スクリプトが呼び出されたパス内のファイルに格納され、 \<scriptname\> $h $ m $s.txt という名前が付けられます。 たとえば、ArchivingPolicy.ps1 を午後12:15 時に実行します。 は、ArchivingPolicy121500.txt などのログファイルを生成します。

5.  最後に、サーバーを構成するための例を提供していますが、負荷の実行が終了したら、構成を変更または削除する必要があることに注意してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

