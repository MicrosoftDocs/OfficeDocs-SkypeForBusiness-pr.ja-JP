---
title: Skype for Business Online の Windows PowerShell コマンドレット、パラメーター、パラメーター値
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9fadf59b353458b2e7c48f597c11b92342e7edc
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Skype for Business Online の Windows PowerShell コマンドレット、パラメーター、パラメーター値

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-05_

すべてのバージョンの Windows で使用されているコマンドウィンドウ (または MS-DOS に精通している場合) に慣れている場合は、Windows PowerShell の使い方について学習します。 コマンドウィンドウで、コマンドを入力し、ENTER キーを押します。 応答として、コンピューターはコマンドまたは実行可能ファイルを実行します。 たとえば、現在のディレクトリにあるすべてのファイルとフォルダーに関する情報を返すには、コマンドプロンプトで次のコマンドを入力し、enter キーを押します。

```console
dir
```

次に、現在のディレクトリにあるすべてのファイルとフォルダーに関する情報を取得します。

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

これは、コマンドまたは実行可能ファイルの名前だけを入力した場合の結果の1つの例です。 ただし、コマンドウィンドウ内から実行されるコマンドの多くでも*引数*を受け取ることができます。 引数とは、コマンドに渡される追加の情報のことで、コマンドの動作を変更します。 たとえば、現在のディレクトリ内のファイルとフォルダーの名前のみを表示したい場合、ファイルやフォルダーのサイズ、フォルダーまたはフォルダーが作成された日付と時刻などの情報は必要ありません。 この場合は、dir コマンドの実行時に **/b**引数を追加します。

```console
dir /b
```

**/B**引数を指定すると、 **dir**コマンドによって、現在のディレクトリにあるフォルダーとファイルの名前だけが返されます。

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

上のコマンドでは、 **/b**引数として、返されるデータをファイル名とフォルダー名に制限するために必要な情報のみを指定します。 これは多くの場合、コマンドラインコマンドと同じように、単に引数が存在する場合に、コマンドの動作を変更するために必要な操作だけです。 (つまり、 **/b**引数を指定して追加情報を非表示にするか、 **/b**引数を除外して追加情報を表示します)。ただし、それ以外の場合は、引数の*値*を指定する必要があります。 引数値は、引数自体に渡す追加情報です。 たとえば、 **/o**引数を使用して、返されるデータをどのように dir コマンドで並べ替えるかを指定できます。 その他のオプションとして、引数値**e**を使用して、ファイル拡張子または引数値**s**で並べ替えて、ファイルサイズで並べ替えることができます。 たとえば、このコマンドは、返されるデータをファイル拡張子で並べ替えます。 引数値**e**は **/o**引数の直後に含まれていることに注意してください。

```console
dir /oe
```

サンプルフォルダーを使用すると、返されるデータは次のようになり、ファイルはファイル拡張子によってアルファベット順に並べ替えられます。

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

また、お客様が何をしているかを正確に把握できるようにします。

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Windows PowerShell ではさまざまな用語を使用していますが、Windows PowerShell を使用するための基本的な方法は、コマンドウィンドウの操作と同じです。コマンドを入力し、必要に応じて引数と引数値を指定し、ENTER キーを押して実行します。それらのコマンド。 ただし、既に説明したように、Windows PowerShell では、コマンドシェルで使用されるものとは異なる用語を使用しています。 Windows PowerShell では、実行するコマンドはコマンド*レット*と呼ばれます。 さらに、コマンドレットに渡される引数は*パラメーター*と呼ばれ、パラメーターに渡される値は*パラメーター値*と呼ばれます。

上記の定義は少し単純化されています。 コマンドレットは、基本的にミニアプリケーションであり、Windows PowerShell 環境内でのみ実行できます。 ただし、コマンドウィンドウから実行できるほとんどのコマンドとアプリケーションなど、Windows PowerShell 内から他のコマンドやアプリケーションを実行することもできます。 たとえば、Windows PowerShell 内からメモ帳を起動する場合は、次のように入力して enter キーを押すだけです。

```console
notepad.exe
```

ただし、Skype for Business Online の管理については、ほとんどの管理者が Windows PowerShell コマンドレットを利用して管理タスクを実行します。 現時点では、Skype for Business Online を管理するために使用できるコマンドやアプリケーションは、他にもいくつかあります。 追加の引数を使わずに、Skype for Business Online のコマンドレットを使うことができる場合があります (詳しくは、「Windows PowerShell でパラメーターと呼ばれる引数」を確認してください)。 たとえば、次のコマンドは、追加のパラメーターを指定せずに、 [Csonline ユーザー](https://technet.microsoft.com/library/JJ994026(v=OCS.15))コマンドレットを呼び出します。 このコマンドは、Skype for Business Online のすべてのユーザーに関する情報を返します。

```powershell
Get-CsOnlineUser
```

ただし、Skype for Business Online のコマンドレットの大半は、パラメーター (およびパラメーター値) も受け取ります。 次のコマンドを検討してください。

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

このコマンドは、次の3つの部分で構成されます。

  - このコマンドレットは、 **Csonline ユーザーを取得**します。

  - Identity パラメーター。 Windows PowerShell では、パラメーターの先頭にダッシュ (-) を付けることに注意してください。 つまり、同じコマンドレットでは、次の構文を使用して UnassignedUser パラメーターが示されます。
    
    ```powershell
    -UnassignedUser
    ```
    
    これは、パラメーターの前にダッシュを付ける必要があるだけでなく、コマンドウィンドウとは異なるため、引数の前にスラッシュ (/) を使用している場合にも知っておくと便利です。
    
    ```console
    /b
    ```

  - パラメーター値**kenmyer@litwareinc.com**。

このコマンドは、kenmyer@litwareinc.com を使って特定のユーザーに関する情報を返します。

<div>

## <a name="see-also"></a>関連項目


[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

