---
title: "Windows PowerShell 3.0 をダウンロードしてインストールします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 5b28607248e2e2778ef4c8832379da0b4d111719
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="24611-103">Windows PowerShell 3.0 をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="24611-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="24611-p101">[] Windows 8.1、Windows 8、Windows Server 2012 R2、または Windows Server 2012 を使用している場合は、既に Windows PowerShell 3.0 がある必要があります。このため、このアプリケーションはこれらのオペレーティング システムでプリインストールされています。</span><span class="sxs-lookup"><span data-stu-id="24611-p101">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0. That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="24611-p102">Windows 7 または Windows Server 2008 R2 を実行している場合は、Windows PowerShell 3.0 も実行している可能性があります。ただし、バージョン 2.0、すなわちこれらのオペレーティング システムで元から提供されているバージョンを実行している可能性もあります。どのバージョンの Microsoft PowerShell を使用しているかを判別するには、お使いの Windows 7 または Windows Server 2008 R2 コンピューターで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="24611-p102">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0. However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems. To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="24611-109">[ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックしてから、[ **Windows PowerShell**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24611-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="24611-110">PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="24611-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="24611-111">次のような情報がコンソール ウィンドウに表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="24611-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="24611-p103">返されたバージョン番号が 3.0 の場合は、Windows PowerShell 3.0 を実行しています。返されたバージョン番号が 3.0 でない場合は、Windows PowerShell 3.0 をインストールする必要があります。Windows PowerShell 3.0 を含んでいる Windows Management Framework 3.0 を、[Microsoft ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=34595)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="24611-p103">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0. If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0. You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="24611-p104">Windows PowerShell 3.0 がインストールされていることを検証した後、PowerShell がリモート スクリプトを実行するために構成されていることを確認する必要があります。これを実行するには、PowerShell を管理者として開始する必要があります。Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 で次を実行します。</span><span class="sxs-lookup"><span data-stu-id="24611-p104">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts. To do that, start PowerShell as an administrator. On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="24611-118">[ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24611-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="24611-119">[ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="24611-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="24611-120">Windows 8 を実行している場合は、代わりにこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="24611-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="24611-p105">チャーム バーにアクセスして、[ **検索**] をクリックしてから [ **Windows PowerShell**] を右クリックします。どの Windows 8 コンピューター (タッチ スクリーンまたはタッチ非対応スクリーン) 上でも、Windows キーを押したままで C をクリックすることによってすばやくチャーム バーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24611-p105">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="24611-123">画面の下部にあるツールバーで、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24611-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="24611-124">[ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="24611-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="24611-p106">PowerShell が実行されている状態になったら、リモート スクリプトの実行を許可するように実行ポリシーを変更する必要があります。PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="24611-p106">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
<span data-ttu-id="24611-127">実行ポリシーが正しく構成されていることを確認するには、PowerShell プロンプトで次を入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="24611-127">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="24611-128">次の値を取り戻したら、すべてが正しく構成されていることになります。</span><span class="sxs-lookup"><span data-stu-id="24611-128">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="24611-p107">現在 Windows PowerShell 3.0 を正しく実行していない場合は Microsoft ダウンロード センターから Windows Management Framework 3.0 をダウンロードしてインストールする必要もあります。これは、Windows PowerShell 3.0 と Windows リモート管理 (WinRM) 3.0 を含んでいるインストール パッケージです。このインストール パッケージは、Windows 7 を実行していて Windows PowerShell 3.0 にまだ更新していない場合に必要となる可能性があります。Windows Server 2012、Windows Server 2012 R2、Windows 8、または Windows 8.1 を実行している場合は、Windows PowerShell 3.0 をインストールする必要はありません。Windows PowerShell 3.0 はこれらのオペレーティング システムでプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="24611-p107">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center. This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0. This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0. If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0. Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="24611-134">Windows Management Framework 3.0 をインストールする前に、次を行います。</span><span class="sxs-lookup"><span data-stu-id="24611-134">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="24611-p108">インストール パッケージの正しいバージョンをダウンロードしたことを確認します。Windows 7 の 64 ビット バージョンを実行している場合は、ファイル Windows6.1-KB2506143-x64.msu をダウンロードします。Windows 7 の 32 ビット バージョンを実行している場合は、ファイル Windows6.1-KB2506143-x86.msu をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="24611-p108">Make sure you have downloaded the correct version of the installation package. If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu. If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="24611-138">コンピューター上で Windows 7 を実行している場合は、Windows 7 Service Pack 1 をインストール済みであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24611-138">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="24611-p109">どのバージョンの Windows を実行しているかわからない場合、または Windows 7 Service Pack 1 をインストール済みであるかわからない場合は、[ **スタート**] をクリックして、[ **コンピューター**] を右クリックしてから [ **プロパティ**] をクリックします。この情報は [システム] ダイアログ ボックスで報告されます。</span><span class="sxs-lookup"><span data-stu-id="24611-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="24611-141">Windows Management Framework 3.0 をインストールするには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="24611-141">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="24611-142">.MSU インストール ファイルi ( **Windows6.1-KB2506143-x64.msu** または **Windows6.1-KB2506143-x86.msu**) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="24611-142">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="24611-143">[更新プログラムのダウンロードとインストール] ウィザードの [ **ライセンス条項をお読みください (1 / 1)**] ページで、[ **同意します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24611-143">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="24611-144">インストールが完了したら、[ **今すぐ再起動**] をクリックしてコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="24611-144">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="24611-p110">コンピューターが再起動した後に、Windows PowerShell が開始できることと、管理者の資格情報でアプリケーションが実行できることを検証します。その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24611-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="24611-147">[ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24611-147">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="24611-148">[ユーザー アカウント制御] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="24611-148">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="24611-p111">PowerShell コンソールが表示されたら、WinRM サービスが実行中で正しく構成されていることを検証する必要があります。サービスが実行されていることを検証するには、次のコマンドを PowerShell プロンプトに入力して ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="24611-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="24611-151">WinRM サービスに関する情報が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24611-151">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="24611-152">サービスの状態が「実行中」を表すものでない場合は、次のコマンドを入力して ENTER を押すことによって WinRM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="24611-152">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="24611-153">サービスが開始した後、次のコマンドを実行して WinRM が基本認証を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24611-153">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="24611-154">次のような情報が画面上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24611-154">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="24611-155">基本認証がある場合は、PowerShell を使用して、Skype のビジネスをオンラインに接続する準備が整ったら、true に設定されています。</span><span class="sxs-lookup"><span data-stu-id="24611-155">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="24611-156">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="24611-156">Related topics</span></span>
[<span data-ttu-id="24611-157">Windows PowerShell 用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="24611-157">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 
