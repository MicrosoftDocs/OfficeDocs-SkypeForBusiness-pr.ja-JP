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

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="4d20a-102">Skype for Business Online の Windows PowerShell コマンドレット、パラメーター、パラメーター値</span><span class="sxs-lookup"><span data-stu-id="4d20a-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d20a-103">_**最終更新日:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="4d20a-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="4d20a-104">すべてのバージョンの Windows で使用されているコマンドウィンドウ (または MS-DOS に精通している場合) に慣れている場合は、Windows PowerShell の使い方について学習します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="4d20a-105">コマンドウィンドウで、コマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="4d20a-106">応答として、コンピューターはコマンドまたは実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="4d20a-107">たとえば、現在のディレクトリにあるすべてのファイルとフォルダーに関する情報を返すには、コマンドプロンプトで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="4d20a-108">次に、現在のディレクトリにあるすべてのファイルとフォルダーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="4d20a-109">これは、コマンドまたは実行可能ファイルの名前だけを入力した場合の結果の1つの例です。</span><span class="sxs-lookup"><span data-stu-id="4d20a-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="4d20a-110">ただし、コマンドウィンドウ内から実行されるコマンドの多くでも*引数*を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="4d20a-111">引数とは、コマンドに渡される追加の情報のことで、コマンドの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="4d20a-112">たとえば、現在のディレクトリ内のファイルとフォルダーの名前のみを表示したい場合、ファイルやフォルダーのサイズ、フォルダーまたはフォルダーが作成された日付と時刻などの情報は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4d20a-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="4d20a-113">この場合は、dir コマンドの実行時に **/b**引数を追加します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="4d20a-114">**/B**引数を指定すると、 **dir**コマンドによって、現在のディレクトリにあるフォルダーとファイルの名前だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="4d20a-115">上のコマンドでは、 **/b**引数として、返されるデータをファイル名とフォルダー名に制限するために必要な情報のみを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="4d20a-116">これは多くの場合、コマンドラインコマンドと同じように、単に引数が存在する場合に、コマンドの動作を変更するために必要な操作だけです。</span><span class="sxs-lookup"><span data-stu-id="4d20a-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="4d20a-117">(つまり、 **/b**引数を指定して追加情報を非表示にするか、 **/b**引数を除外して追加情報を表示します)。ただし、それ以外の場合は、引数の*値*を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d20a-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="4d20a-118">引数値は、引数自体に渡す追加情報です。</span><span class="sxs-lookup"><span data-stu-id="4d20a-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="4d20a-119">たとえば、 **/o**引数を使用して、返されるデータをどのように dir コマンドで並べ替えるかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="4d20a-120">その他のオプションとして、引数値**e**を使用して、ファイル拡張子または引数値**s**で並べ替えて、ファイルサイズで並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="4d20a-121">たとえば、このコマンドは、返されるデータをファイル拡張子で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="4d20a-122">引数値**e**は **/o**引数の直後に含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4d20a-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="4d20a-123">サンプルフォルダーを使用すると、返されるデータは次のようになり、ファイルはファイル拡張子によってアルファベット順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="4d20a-124">また、お客様が何をしているかを正確に把握できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4d20a-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="4d20a-125">Windows PowerShell ではさまざまな用語を使用していますが、Windows PowerShell を使用するための基本的な方法は、コマンドウィンドウの操作と同じです。コマンドを入力し、必要に応じて引数と引数値を指定し、ENTER キーを押して実行します。それらのコマンド。</span><span class="sxs-lookup"><span data-stu-id="4d20a-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="4d20a-126">ただし、既に説明したように、Windows PowerShell では、コマンドシェルで使用されるものとは異なる用語を使用しています。</span><span class="sxs-lookup"><span data-stu-id="4d20a-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="4d20a-127">Windows PowerShell では、実行するコマンドはコマンド*レット*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="4d20a-128">さらに、コマンドレットに渡される引数は*パラメーター*と呼ばれ、パラメーターに渡される値は*パラメーター値*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="4d20a-129">上記の定義は少し単純化されています。</span><span class="sxs-lookup"><span data-stu-id="4d20a-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="4d20a-130">コマンドレットは、基本的にミニアプリケーションであり、Windows PowerShell 環境内でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="4d20a-131">ただし、コマンドウィンドウから実行できるほとんどのコマンドとアプリケーションなど、Windows PowerShell 内から他のコマンドやアプリケーションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="4d20a-132">たとえば、Windows PowerShell 内からメモ帳を起動する場合は、次のように入力して enter キーを押すだけです。</span><span class="sxs-lookup"><span data-stu-id="4d20a-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="4d20a-133">ただし、Skype for Business Online の管理については、ほとんどの管理者が Windows PowerShell コマンドレットを利用して管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="4d20a-134">現時点では、Skype for Business Online を管理するために使用できるコマンドやアプリケーションは、他にもいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4d20a-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="4d20a-135">追加の引数を使わずに、Skype for Business Online のコマンドレットを使うことができる場合があります (詳しくは、「Windows PowerShell でパラメーターと呼ばれる引数」を確認してください)。</span><span class="sxs-lookup"><span data-stu-id="4d20a-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="4d20a-136">たとえば、次のコマンドは、追加のパラメーターを指定せずに、 [Csonline ユーザー](https://technet.microsoft.com/library/JJ994026(v=OCS.15))コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="4d20a-137">このコマンドは、Skype for Business Online のすべてのユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="4d20a-138">ただし、Skype for Business Online のコマンドレットの大半は、パラメーター (およびパラメーター値) も受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4d20a-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="4d20a-139">次のコマンドを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4d20a-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="4d20a-140">このコマンドは、次の3つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="4d20a-141">このコマンドレットは、 **Csonline ユーザーを取得**します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="4d20a-142">Identity パラメーター。</span><span class="sxs-lookup"><span data-stu-id="4d20a-142">The Identity parameter.</span></span> <span data-ttu-id="4d20a-143">Windows PowerShell では、パラメーターの先頭にダッシュ (-) を付けることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4d20a-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="4d20a-144">つまり、同じコマンドレットでは、次の構文を使用して UnassignedUser パラメーターが示されます。</span><span class="sxs-lookup"><span data-stu-id="4d20a-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="4d20a-145">これは、パラメーターの前にダッシュを付ける必要があるだけでなく、コマンドウィンドウとは異なるため、引数の前にスラッシュ (/) を使用している場合にも知っておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="4d20a-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="4d20a-146">パラメーター値**kenmyer@litwareinc.com**。</span><span class="sxs-lookup"><span data-stu-id="4d20a-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="4d20a-147">このコマンドは、kenmyer@litwareinc.com を使って特定のユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4d20a-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d20a-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d20a-148">See Also</span></span>


<span data-ttu-id="4d20a-149">[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d20a-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

