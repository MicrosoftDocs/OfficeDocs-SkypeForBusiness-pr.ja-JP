---
title: Skype for Business Online の Windows PowerShell コマンドレット、パラメーター、およびパラメーター値
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499964"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Skype for Business Online の Windows PowerShell コマンドレット、パラメーター、およびパラメーター値

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-05_

すべてのバージョンの Windows (または MS-DOS に精通している場合) にあるコマンドウィンドウを使い慣れている場合は、Windows PowerShell の使用方法を学習する際に、すぐに開始できます。 コマンドウィンドウで、コマンドを入力して ENTER キーを押します。 応答として、コンピューターはコマンドまたは実行可能ファイルを実行します。 たとえば、現在のディレクトリ内のすべてのファイルとフォルダーに関する情報を戻すには、コマンドプロンプトで次のコマンドを入力し、enter キーを押します。

```console
dir
```

その後、現在のディレクトリ内のすべてのファイルとフォルダーに関する情報を取得します。

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

これは、コマンドまたは実行可能ファイルの名前のみを入力した場合の結果の一例です。 ただし、コマンドウィンドウ内で実行されるコマンドの多くは、 *引数*を受け取ることもあります。 引数は、コマンドに渡される追加の情報です。これにより、コマンドの動作が変更されます。 たとえば、現在のディレクトリ内のファイルとフォルダーの名前のみを表示する場合は、ファイルやフォルダーのサイズ、フォルダーまたはフォルダーが作成された日付と時刻などの情報は含まれません。 この場合は、dir コマンドを実行するときに **/b** 引数を追加します。

```console
dir /b
```

**/B**引数を指定すると、 **dir**コマンドによって、現在のディレクトリ内のフォルダーとファイルの名前のみが返されます。

```console
Deploy
Intel
PerfLogs
Program Files
Program Files (x86)
Users
Windows
pldok.log
RHDSetup.exe
setup.doc
```

上記のコマンドで、 **/b 引数/b** は、返されるデータをファイルおよびフォルダー名に制限するために必要な情報のみを示しています。 多くの場合、コマンドラインコマンドを使用すると、単に引数が存在するだけで、コマンドの動作を変更する必要があります。 (つまり、 **/b 引数/b** を指定して追加情報を非表示にしたり、 **/b** 引数を除外して追加情報を表示したりすることができます)。ただし、その他の場合は、引数の *値*を指定する必要があります。 引数の値は、引数自体に渡される追加情報です。 たとえば、 **/o** 引数を使用すると、dir コマンドで返されるデータを並べ替える方法を指定できます。 その他のオプションとして、引数の値 **e** を使用してファイル拡張子または引数 **の値で** 並べ替えて、ファイルサイズで並べ替えることができます。 たとえば、このコマンドは、返されるデータをファイル拡張子で並べ替えます。 引数 **/o**の直後に引数の値**e**が含まれていることに注意してください。

```console
dir /oe
```

サンプルフォルダーを使用すると、返されるデータは次のようになります。ファイルは、アルファベット順でファイル拡張子で並べ替えられます。

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

また、次の内容を正確に特定するのに役立ちます。

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Windows PowerShell はさまざまな用語を使用しますが、Windows PowerShell で作業するための基本的な方法は、コマンドウィンドウを使用する方法と同じです。コマンドを入力し、必要に応じて引数と引数の値を指定した後、ENTER キーを押してそれらのコマンドを実行します。 前述したように、Windows PowerShell では、コマンドシェルで使用される用語とは異なる用語が使用されます。 Windows PowerShell では、実行するコマンドはコマンド *レット*と呼ばれます。 また、コマンドレットに渡される引数は、 *パラメーターと呼ばれ、パラメーター*に渡される値はパラメーター *値*と呼ばれます。

前述の定義は少し簡略化されています。 コマンドレットは基本的にミニアプリケーションであり、Windows PowerShell 環境からのみ実行できます。 ただし、コマンドウィンドウから実行できるコマンドやアプリケーションの大部分を含む、Windows PowerShell からその他のコマンドとアプリケーションを実行することもできます。 たとえば、Windows PowerShell 内からメモ帳を起動するには、次のように入力して enter キーを押します。

```console
notepad.exe
```

ただし、Skype for Business Online の管理には、ほとんどの管理者が Windows PowerShell コマンドレットに依存して管理タスクを実行します。 ときには、Skype for Business Online の管理に使用できるコマンドやアプリケーションの種類はほとんどありません。 場合によっては、追加の引数を指定せずに Skype for Business Online のコマンドレットを使用することもできます (前述のように、引数は Windows PowerShell ではパラメーターと呼ばれます)。 たとえば、次のコマンドは、追加のパラメーターを指定せずに、 [ユーザー](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) コマンドレットを呼び出します。 コマンドは単独で、Skype for Business Online のすべてのユーザーに関する情報を返します。

```powershell
Get-CsOnlineUser
```

ただし、ほとんどの Skype for Business Online コマンドレットでは、パラメーター (およびパラメーター値) も使用できます。 次のコマンドを考えてみます。

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

このコマンドは、次の3つの部分で構成されます。

  - コマンドレットは、 **Csonline ユーザーを取得**します。

  - Identity パラメーター。 Windows PowerShell では、パラメーターの先頭にダッシュ (-) が付いていることに注意してください。 これは、この同じコマンドレットでは、次の構文を使用して UnassignedUser パラメーターが示されることを意味します。
    
    ```powershell
    -UnassignedUser
    ```
    
    これは、パラメーターの前にダッシュを付ける必要があるだけでなく、引数が先頭にスラッシュ (/) を使用して指定されているからです。
    
    ```console
    /b
    ```

  - パラメーター値 **kenmyer@litwareinc.com**。

ちなみに、このコマンドは、特定のユーザーに関する情報を返します。これは、id が kenmyer@litwareinc.com のユーザーです。

<div>

## <a name="see-also"></a>関連項目


[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

