---
title: "ダウンロードして、Windows PowerShell 3.0 をインストールする."
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
description: "ダウンロード、インストール、および Windows PowerShell 3.0 を使用して、Skype for Business Online に接続するためのリモート PowerShell セッションを作成します。"
ms.openlocfilehash: c3fddb71c677e602332adc5b564627969552d4c9
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="9c597-103">ダウンロードして、Windows PowerShell 3.0 をインストールする.</span><span class="sxs-lookup"><span data-stu-id="9c597-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="9c597-p101">Windows 8.1、Windows 8、Windows Server 2012 R2 または Windows Server 2012 を使用している場合は、Windows PowerShell 3.0 既にが必要です。このアプリケーションは、これらのオペレーティング システムがあらかじめインストールされているためにです。</span><span class="sxs-lookup"><span data-stu-id="9c597-p101">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0. That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="9c597-p102">Windows 7 または Windows Server 2008 R2 を実行している場合は、Windows PowerShell 3.0 を実行するも可能性があります。ただし、こともする可能性がありますが実行されているバージョン 2.0 代わりに、これらのオペレーティング システムに同梱されていたバージョンです。使用している Microsoft PowerShelll のバージョンを確認するのには、Windows 7 または Windows Server 2008 R2 のコンピューターに次を手順します。</span><span class="sxs-lookup"><span data-stu-id="9c597-p102">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0. However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems. To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="9c597-109">[**スタート**] ボタン**すべてのプログラム**] をクリックして、[**アクセサリ**] をクリックして、 **Windows PowerShell**を**Windows PowerShell**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9c597-110">PowerShell コンソールで、次のコマンドを入力し、[ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c597-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="9c597-111">コンソール ウィンドウで、[次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c597-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="9c597-p103">返されるバージョン番号が 3.0 の場合は、Windows PowerShell 3.0 を実行しています。返されるバージョン番号が 3.0 でない場合は、Windows PowerShell 3.0 をインストールする必要があります。Windows PowerShell 3.0 が含まれている Windows Management Framework 3.0 は、 [Microsoft ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=34595)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9c597-p103">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0. If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0. You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="9c597-p104">Windows PowerShell 3.0 がインストールされていることを確認した後、PowerShell がリモート スクリプトを実行するために構成されていることを確認してください。そのため、管理者として PowerShell を起動します。Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c597-p104">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts. To do that, start PowerShell as an administrator. On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="9c597-118">[**スタート**] ボタン**すべてのプログラム**] をクリックして、[**アクセサリ**] をクリックして、 **Windows PowerShell**、 **Windows PowerShell**を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="9c597-119">[**ユーザー アカウント制御**] ダイアログ ボックスが表示されている場合は、管理者の資格情報の下で、PowerShell を実行することを確認するのに**[はい]**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="9c597-120">Windows 8 を実行している場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c597-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="9c597-p105">チャーム バーのアクセス、**検索**] をクリックし、 **Windows PowerShell**を右クリックします。チャーム バーで、任意の Windows 8 コンピューター (タッチ スクリーンまたは非タッチ画面) は、Windows キーを押しながら C キーを押して、すばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9c597-p105">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="9c597-123">ツールバーで、画面の下部にある、**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="9c597-124">[**ユーザー アカウント制御**] ダイアログ ボックスが表示されている場合は、管理者の資格情報の下で、PowerShell を実行することを確認するのに**[はい]**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="9c597-p106">PowerShell の実行後に、リモート スクリプトの実行を許可する実行ポリシーを変更する必要があります。PowerShell コンソールで、次のコマンドを入力し、[ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c597-p106">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
<span data-ttu-id="9c597-127">実行ポリシーが正しく構成されていることを確認するには、PowerShell のプロンプトで、次を入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c597-127">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="9c597-128">次の値を戻ることがある場合、[すべてのアイテムが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="9c597-128">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="9c597-p107">Windows PowerShell 3.0 を現在実行されていない場合も、ダウンロードして、Microsoft ダウンロード センターから Windows Management Framework 3.0 をインストールする必要があります。これは、Windows PowerShell 3.0 および Windows リモート管理 (WinRM) 3.0 を含むインストール パッケージです。Windows 7 を実行し、Windows PowerShell 3.0 に更新がいない場合は、このインストール パッケージが必要になる場合があります。Windows Server 2012、Windows Server 2012 R2、Windows 8 または Windows 8.1 を実行している場合は、Windows PowerShell 3.0 をインストールする必要がありますいけません。Windows PowerShell 3.0 は、これらのオペレーティング システムであらかじめインストールされているできます。</span><span class="sxs-lookup"><span data-stu-id="9c597-p107">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center. This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0. This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0. If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0. Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="9c597-134">Windows Management Framework 3.0 をインストールするには: する前に</span><span class="sxs-lookup"><span data-stu-id="9c597-134">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="9c597-p108">適切なバージョンのインストール パッケージをダウンロードすることを確認します。64 ビット バージョンの Windows 7 を実行している場合は、Windows6.1-KB2506143-x64.msu ファイルをダウンロードします。32 ビット バージョンの Windows 7 を実行している場合は、Windows6.1-KB2506143-x86.msu ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9c597-p108">Make sure you have downloaded the correct version of the installation package. If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu. If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="9c597-138">お使いのコンピューターで Windows 7 を実行している場合は、Windows 7 の Service Pack 1 がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c597-138">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="9c597-p109">不明な場合 Windows のバージョンを実行しているかが不明な Windows 7 の Service Pack 1 のインストールを**開始**] をクリックして、**コンピューター**を右クリックし、[**プロパティ**] をクリックします。[システム] ダイアログ ボックスでこの情報が報告されます。</span><span class="sxs-lookup"><span data-stu-id="9c597-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="9c597-141">Windows Management Framework 3.0 をインストールするのには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="9c597-141">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="9c597-142">ダブルクリックします。MSU インストール ファイル ( **Windows6.1-KB2506143-x64.msu**または**Windows6.1-KB2506143-x86.msu**)。</span><span class="sxs-lookup"><span data-stu-id="9c597-142">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="9c597-143">ダウンロードおよび更新プログラムのインストール ウィザードで、**この使用許諾条項 (1/1) の読み取り**] ページで、[**同意**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-143">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="9c597-144">インストールが完了したら、 **[今すぐ再起動**お使いのコンピューターを再起動するのにをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-144">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="9c597-p110">コンピューターの再起動後に Windows PowerShell を開始することを管理者の資格情報、アプリケーションを実行できることを確認します。これを行うには。</span><span class="sxs-lookup"><span data-stu-id="9c597-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="9c597-147">[**スタート**] ボタン**すべてのプログラム**] をクリックして、[**アクセサリ**] をクリックして、 **Windows PowerShell**、 **Windows PowerShell**を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c597-147">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="9c597-148">管理者の資格情報で PowerShell を実行する場合は、ユーザー アカウント制御] ダイアログ ボックスが表示されたら、 **[はい**] をクリックしてことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c597-148">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="9c597-p111">PowerShell コンソールが表示されたらは、WinRM サービスが実行されていると正しく構成されていることを確認してください。サービスが実行されていることを確認するには、PowerShell のプロンプトで、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c597-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="9c597-151">WinRM サービスについての情報が、[画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c597-151">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="9c597-152">サービスの状態ではない「を実行している」場合、は、次のコマンドを入力し、ENTER を押すことによって WinRM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="9c597-152">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="9c597-153">サービスを開始した後、WinRM が基本認証を使用しているかどうかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c597-153">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="9c597-154">画面に表示されるには、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c597-154">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="9c597-155">場合は、Skype for Business Online に接続する PowerShell を使用する準備ができたら、基本認証を true に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9c597-155">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="9c597-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c597-156">Related topics</span></span>
[<span data-ttu-id="9c597-157">Windows PowerShell の自分のコンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="9c597-157">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 
