---
title: LyncPerfTool を実行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daf46c5e34558a719cdf4fafa15a57f273c4030d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>LyncPerfTool を実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

Lync Server 2013 応力とパフォーマンスツール (LyncPerfTool) を実行する前に、ユーザー、連絡先、シナリオを作成する必要があります。 これらの操作を実行するためのツールの使用について詳しくは、「[ユーザーと連絡先を作成](create-users-and-contacts.md)して、[ユーザープロファイルを構成](configure-user-profile.md)する」をご覧ください。 これらのツールを実行すると、必要なパラメーターが含まれているバッチファイルの一部として LyncPerfTool を実行するファイルも生成されます。

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 のストレスとパフォーマンスのツールを実行する

UserProfileGenerator ツールによって、LyncPerfTool のパフォーマンスカウンターを登録し、XML 構成ファイルを読み込むことによって LyncPerfTool を実行できるバッチファイルが作成されます。 バッチファイルは、構成ファイルごとに LyncPerfTool の1つのインスタンスを実行します。 バッチファイルを実行するには、次の操作を行います。

1.  構成フォルダーとファイルを含むフォルダーを、各クライアントコンピューター上の LyncStressTool を含むディレクトリにコピーします。 (たとえば、1.28\_13.16.16 という名前のフォルダーで構成ファイルを生成した場合は、各クライアントに LyncPerfTool が含まれているフォルダーにそのフォルダーをコピーします)。

2.  適切に番号付けされたクライアントフォルダーに移動し、RunClient バッチスクリプトを実行します。 Windows エクスプローラーでバッチファイルをダブルクリックするだけで、そのクライアント番号のすべての構成ファイルが実行されます。 次の構文を使用して、適切なクライアントフォルダーからスクリプトを実行することもできます。

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
LyncPerfTool を直接実行するには、コマンドプロンプトを開き、コマンドラインで次のコマンドを入力します (初めて実行する場合は、この後のメモに示すように、パフォーマンスカウンター regsvr32/i/n/s LyncPerfToolPerf を登録してください。トピック): LyncPerfTool:\<configxml\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
このツールで構成ファイルの値を表示するには、次のように、前のコマンドに「/displayfile」パラメーターを含めます。
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
プロセスを終了するには、Ctrl キーを押しながら C キーを押します。

<div>


> [!NOTE]  
> LyncPerfTool を直接実行する前に、パフォーマンスカウンターを登録する必要があります。 パフォーマンスカウンターを登録するには、次のコマンドを入力します。



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 開始した LyncPerfTool のすべてのインスタンスは、通常、ユーザーが1秒あたり1人のユーザーとして、すぐにユーザーのサインインを開始します。 プールのピークユーザーのサインイン速度は約 12/秒です。 これは、ユーザーがまだサインインしている間に、12個を超える LyncPerfTool インスタンスを同時に開始しないことを意味します。 1000ユーザーは、1秒あたり最大20分でサインインすることになります。



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

