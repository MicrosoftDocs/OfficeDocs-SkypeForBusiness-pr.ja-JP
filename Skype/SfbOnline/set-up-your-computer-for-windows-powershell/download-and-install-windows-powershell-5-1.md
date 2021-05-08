---
title: Windows PowerShell 5.1 をダウンロードしてインストールする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Windows PowerShell 5.1 のダウンロードとインストールを行い、これを使用して Skype for Business Online に接続するリモート PowerShell セッションを作成します。
ms.openlocfilehash: fb73ccdf63cc64cbe309de1ff5223090d1c282bb
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239334"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="bff1f-103">Windows PowerShell 5.1 をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="bff1f-103">Download and install Windows PowerShell 5.1</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="bff1f-104">Windows 10 Anniversary Update または Windows Server 2016 を使用している場合は、Windows PowerShell 5.1 が既にインストールされているはずです。</span><span class="sxs-lookup"><span data-stu-id="bff1f-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="bff1f-105">このアプリケーションはこれらのオペレーティング システムにプリインストールされているためです。</span><span class="sxs-lookup"><span data-stu-id="bff1f-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="bff1f-106">ご使用中の Microsoft PowerShell のバージョンを特定するには、Windows 7 または Windows Server 2008 R2 もしくは Windows Server 2012 のコンピューターで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="bff1f-107">[ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックしてから、[ **Windows PowerShell**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bff1f-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bff1f-108">PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="bff1f-109">次のような情報がコンソール ウィンドウに表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="bff1f-110">返されたバージョン番号が 5.1 の場合は、Windows PowerShell 5.1 を実行しています。</span><span class="sxs-lookup"><span data-stu-id="bff1f-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="bff1f-111">返されたバージョン番号が 5.1 ではない場合は、Windows PowerShell 5.1 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="bff1f-112">Windows PowerShell 5.1 が含まれている Windows Management Framework 5.1 を [Microsoft ダウンロード センター](https://www.microsoft.com/download/details.aspx?id=54616)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bff1f-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="bff1f-113">Windows PowerShell 5.1 がインストールされていることを確認した後に、PowerShell がリモート スクリプトを実行するために構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="bff1f-114">これを実行するには、PowerShell を管理者として開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="bff1f-115">Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 で次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="bff1f-116">[ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bff1f-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="bff1f-117">[ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="bff1f-118">Windows 8 を実行している場合は、代わりにこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="bff1f-p104">チャーム バーにアクセスして、[ **検索**] をクリックしてから [ **Windows PowerShell**] を右クリックします。どの Windows 8 コンピューター (タッチ スクリーンまたはタッチ非対応スクリーン) 上でも、Windows キーを押したままで C をクリックすることによってすばやくチャーム バーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bff1f-p104">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="bff1f-121">画面の下部にあるツールバーで、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bff1f-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="bff1f-122">[ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="bff1f-p105">PowerShell が実行されている状態になったら、リモート スクリプトの実行を許可するように実行ポリシーを変更する必要があります。PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-p105">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="bff1f-125">前述のコマンドを実行すると次のエラー メッセージが表示されることがあります: *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span><span class="sxs-lookup"><span data-stu-id="bff1f-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="bff1f-126">このエラー メッセージは通常、管理者の資格情報で PowerShell を実行していない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="bff1f-127">PowerShell のセッションを閉じ、管理者として新しいセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="bff1f-128">実行ポリシーが正しく構成されていることを確認するには、PowerShell プロンプトで次を入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="bff1f-129">次の値を取り戻したら、すべてが正しく構成されていることになります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="bff1f-130">現在 Windows PowerShell 5.1 を実行していない場合は Microsoft ダウンロード センターから Windows Management Framework 5.1 をダウンロードしてインストールする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="bff1f-131">これは、Windows PowerShell 5.1 と Windows リモート管理 (WinRM) 3.0 が含まれているインストール パッケージです。</span><span class="sxs-lookup"><span data-stu-id="bff1f-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="bff1f-132">このインストール パッケージは、Windows 7 SP1 を実行していて Windows PowerShell 5.1 にまだ更新していない場合に必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bff1f-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="bff1f-133">Windows Server 2016 または Windows 10 Anniversary Update を実行している場合は、Windows PowerShell 5.1 をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bff1f-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="bff1f-134">Windows PowerShell 5.1 はこれらのオペレーティング システムにプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bff1f-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="bff1f-135">Windows Management Framework 5.1 をインストールする前に次を行います。</span><span class="sxs-lookup"><span data-stu-id="bff1f-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="bff1f-136">正しいバージョンのインストール パッケージをダウンロードしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="bff1f-137">Windows 7 SP1 の 64 ビット版を実行している場合は、ファイル Win7AndW2K8R2-KB3191566-x64.ZIP をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bff1f-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="bff1f-138">Windows 7 の 32 ビット版を実行している場合は、ファイル Win7-KB3191566-x86.ZIP をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bff1f-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="bff1f-139">コンピューター上で Windows 7 を実行している場合は、Windows 7 Service Pack 1 をインストール済みであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="bff1f-p109">どのバージョンの Windows を実行しているかわからない場合、または Windows 7 Service Pack 1 をインストール済みであるかわからない場合は、[ **スタート**] をクリックして、[ **コンピューター**] を右クリックしてから [ **プロパティ**] をクリックします。この情報は [システム] ダイアログ ボックスで報告されます。</span><span class="sxs-lookup"><span data-stu-id="bff1f-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="bff1f-142">Windows Management Framework 5.1 をインストールするには、「[WMF 5.1 のインストールと構成](/powershell/scripting/wmf/setup/install-configure)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="bff1f-p110">コンピューターが再起動した後に、Windows PowerShell が開始できることと、管理者の資格情報でアプリケーションが実行できることを検証します。その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bff1f-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="bff1f-145">[ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bff1f-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="bff1f-146">[ユーザー アカウント制御] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="bff1f-p111">PowerShell コンソールが表示されたら、WinRM サービスが実行中で正しく構成されていることを検証する必要があります。サービスが実行されていることを検証するには、次のコマンドを PowerShell プロンプトに入力して ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="bff1f-149">WinRM サービスに関する情報が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff1f-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="bff1f-150">サービスの状態が「実行中」を表すものでない場合は、次のコマンドを入力して ENTER を押すことによって WinRM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="bff1f-151">サービスが開始した後、次のコマンドを実行して WinRM が基本認証を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff1f-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="bff1f-152">次のような情報が画面上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff1f-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="bff1f-153">基本認証が True に設定されている場合、PowerShell を使用して Skype for Business Online に接続する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="bff1f-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="bff1f-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bff1f-154">Related topics</span></span>
[<span data-ttu-id="bff1f-155">Windows PowerShell 用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bff1f-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
