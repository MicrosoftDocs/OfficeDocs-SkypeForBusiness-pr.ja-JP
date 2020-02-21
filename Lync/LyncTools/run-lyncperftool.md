---
title: LyncPerfTool を実行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4c7d7de6dcb2f2eee15e7da0809dd6e3c41e07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>LyncPerfTool を実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool) を実行する前に、ユーザー、連絡先、およびシナリオを作成する必要があります。 これらの操作を実行するためのツールの使用の詳細については、「 [Create Users And Contacts](create-users-and-contacts.md) 」および「 [Configure User Profile](configure-user-profile.md)」を参照してください。 これらのツールを実行すると、必要なパラメーターが含まれるバッチファイルの一部として LyncPerfTool を実行するファイルも生成されます。

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 ストレスおよびパフォーマンスツールの実行

Userprofilegenerator.exe ツールは、LyncPerfTool パフォーマンスカウンターを登録し、XML 構成ファイルを読み込むことによって LyncPerfTool を実行できるバッチファイルを作成します。 バッチファイルでは、構成ファイルごとに LyncPerfTool の1つのインスタンスが実行されます。 バッチファイルを実行するには、次の操作を行います。

1.  構成フォルダーとファイルが格納されているフォルダーを、各クライアントコンピューター上の LyncStressTool が格納されているディレクトリにコピーします。 (たとえば、1.28\_13.16.16 という名前のフォルダーに構成ファイルを生成した場合、そのフォルダーを各クライアント上の LyncPerfTool を含むフォルダーにコピーします。)

2.  適切な番号が付けられたクライアントフォルダーに移動し、RunClient バッチスクリプトを実行します。 Windows Explorer でバッチファイルをダブルクリックするだけで、そのクライアント番号のすべての構成ファイルが実行されます。 また、次の構文を使用して、適切なクライアントフォルダーからスクリプトを実行することもできます。

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
LyncPerfTool を直接実行するには、コマンドプロンプトを開き、コマンドラインで次のコマンドを入力します (この操作を初めて実行するときは、このトピックで後述する「メモ」に示すように、パフォーマンスカウンター regsvr32/i/n/s LyncPerfToolPerf を登録してください)。\<LyncPerfTool の設定: configxml\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
構成ファイルの値をツールに表示するには、次のように、上記のコマンドに、次のようにして、/displayfile パラメーターを含めます。
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
プロセスを終了するには、Ctrl + C キーを押します。

<div>


> [!NOTE]  
> LyncPerfTool を直接実行する前に、パフォーマンスカウンターを登録する必要があります。 次のコマンドを入力して、パフォーマンスカウンターを登録します。



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 開始する LyncPerfTool のすべてのインスタンスは、通常、1秒あたり1ユーザーの料金で、ユーザーのサインインを直ちに開始します。 プールのピークユーザーのサインイン率は約 12/秒です。 これは、ユーザーがまだサインインしている間、12個を超える LyncPerfTool インスタンスを同時に開始してはならないことを意味します。 1000ユーザーが完全にサインインするには、1秒あたり約20分かかります。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[ユーザーと連絡先を作成する](create-users-and-contacts.md)  
[ユーザープロファイルを構成する](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

