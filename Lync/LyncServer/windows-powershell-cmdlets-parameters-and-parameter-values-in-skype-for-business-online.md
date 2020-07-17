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
ms.openlocfilehash: 70c7b04c428297e74d0910a42c4136bf4a06dacd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="b7012-102">Skype for Business Online の Windows PowerShell コマンドレット、パラメーター、およびパラメーター値</span><span class="sxs-lookup"><span data-stu-id="b7012-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7012-103">_**トピックの最終更新日:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="b7012-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="b7012-104">すべてのバージョンの Windows (または MS-DOS に精通している場合) にあるコマンドウィンドウを使い慣れている場合は、Windows PowerShell の使用方法を学習する際に、すぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="b7012-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="b7012-105">コマンドウィンドウで、コマンドを入力して ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b7012-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="b7012-106">応答として、コンピューターはコマンドまたは実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7012-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="b7012-107">たとえば、現在のディレクトリ内のすべてのファイルとフォルダーに関する情報を戻すには、コマンドプロンプトで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b7012-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="b7012-108">その後、現在のディレクトリ内のすべてのファイルとフォルダーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7012-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="b7012-109">これは、コマンドまたは実行可能ファイルの名前のみを入力した場合の結果の一例です。</span><span class="sxs-lookup"><span data-stu-id="b7012-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="b7012-110">ただし、コマンドウィンドウ内で実行されるコマンドの多くは、*引数*を受け取ることもあります。</span><span class="sxs-lookup"><span data-stu-id="b7012-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="b7012-111">引数は、コマンドに渡される追加の情報です。これにより、コマンドの動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="b7012-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="b7012-112">たとえば、現在のディレクトリ内のファイルとフォルダーの名前のみを表示する場合は、ファイルやフォルダーのサイズ、フォルダーまたはフォルダーが作成された日付と時刻などの情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b7012-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="b7012-113">この場合は、dir コマンドを実行するときに **/b**引数を追加します。</span><span class="sxs-lookup"><span data-stu-id="b7012-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="b7012-114">**/B**引数を指定すると、 **dir**コマンドによって、現在のディレクトリ内のフォルダーとファイルの名前のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="b7012-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="b7012-115">上記のコマンドで、 **/b 引数/b**は、返されるデータをファイルおよびフォルダー名に制限するために必要な情報のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="b7012-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="b7012-116">多くの場合、コマンドラインコマンドを使用すると、単に引数が存在するだけで、コマンドの動作を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7012-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="b7012-117">(つまり、 **/b 引数/b**を指定して追加情報を非表示にしたり、 **/b**引数を除外して追加情報を表示したりすることができます)。ただし、その他の場合は、引数の*値*を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7012-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="b7012-118">引数の値は、引数自体に渡される追加情報です。</span><span class="sxs-lookup"><span data-stu-id="b7012-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="b7012-119">たとえば、 **/o**引数を使用すると、dir コマンドで返されるデータを並べ替える方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b7012-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="b7012-120">その他のオプションとして、引数の値**e**を使用してファイル拡張子または引数**の値で**並べ替えて、ファイルサイズで並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b7012-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="b7012-121">たとえば、このコマンドは、返されるデータをファイル拡張子で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="b7012-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="b7012-122">引数 **/o**の直後に引数の値**e**が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7012-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="b7012-123">サンプルフォルダーを使用すると、返されるデータは次のようになります。ファイルは、アルファベット順でファイル拡張子で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="b7012-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="b7012-124">また、次の内容を正確に特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b7012-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="b7012-125">Windows PowerShell はさまざまな用語を使用しますが、Windows PowerShell で作業するための基本的な方法は、コマンドウィンドウを使用する方法と同じです。コマンドを入力し、必要に応じて引数と引数の値を指定した後、ENTER キーを押してそれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7012-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="b7012-126">前述したように、Windows PowerShell では、コマンドシェルで使用される用語とは異なる用語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7012-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="b7012-127">Windows PowerShell では、実行するコマンドはコマンド*レット*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b7012-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="b7012-128">また、コマンドレットに渡される引数は、*パラメーターと呼ばれ、パラメーター*に渡される値はパラメーター*値*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b7012-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="b7012-129">前述の定義は少し簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="b7012-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="b7012-130">コマンドレットは基本的にミニアプリケーションであり、Windows PowerShell 環境からのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="b7012-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="b7012-131">ただし、コマンドウィンドウから実行できるコマンドやアプリケーションの大部分を含む、Windows PowerShell からその他のコマンドとアプリケーションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7012-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="b7012-132">たとえば、Windows PowerShell 内からメモ帳を起動するには、次のように入力して enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b7012-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="b7012-133">ただし、Skype for Business Online の管理には、ほとんどの管理者が Windows PowerShell コマンドレットに依存して管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7012-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="b7012-134">ときには、Skype for Business Online の管理に使用できるコマンドやアプリケーションの種類はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="b7012-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="b7012-135">場合によっては、追加の引数を指定せずに Skype for Business Online のコマンドレットを使用することもできます (前述のように、引数は Windows PowerShell ではパラメーターと呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="b7012-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="b7012-136">たとえば、次のコマンドは、追加のパラメーターを指定せずに、[ユーザー](https://technet.microsoft.com/library/JJ994026(v=OCS.15))コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b7012-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="b7012-137">コマンドは単独で、Skype for Business Online のすべてのユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b7012-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="b7012-138">ただし、ほとんどの Skype for Business Online コマンドレットでは、パラメーター (およびパラメーター値) も使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7012-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="b7012-139">次のコマンドを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="b7012-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="b7012-140">このコマンドは、次の3つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b7012-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="b7012-141">コマンドレットは、 **Csonline ユーザーを取得**します。</span><span class="sxs-lookup"><span data-stu-id="b7012-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="b7012-142">Identity パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b7012-142">The Identity parameter.</span></span> <span data-ttu-id="b7012-143">Windows PowerShell では、パラメーターの先頭にダッシュ (-) が付いていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7012-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="b7012-144">これは、この同じコマンドレットでは、次の構文を使用して UnassignedUser パラメーターが示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7012-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="b7012-145">これは、パラメーターの前にダッシュを付ける必要があるだけでなく、引数が先頭にスラッシュ (/) を使用して指定されているからです。</span><span class="sxs-lookup"><span data-stu-id="b7012-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="b7012-146">パラメーター値**kenmyer@litwareinc.com**。</span><span class="sxs-lookup"><span data-stu-id="b7012-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="b7012-147">ちなみに、このコマンドは、特定のユーザーに関する情報を返します。これは、id が kenmyer@litwareinc.com のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b7012-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b7012-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7012-148">See Also</span></span>


<span data-ttu-id="b7012-149">[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b7012-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

