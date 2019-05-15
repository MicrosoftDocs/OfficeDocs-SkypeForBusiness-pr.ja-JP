---
title: Skype for Business Online Connector モジュールをダウンロードしてインストールする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036694"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="f57cd-103">Skype for Business Online Connector モジュールをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="f57cd-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="f57cd-104">[] Skype for Business Online Connector モジュール には、 **New-CsOnlineSession** Windows PowerShell に接続するリモート Skype for Business Online セッションを作成できるようにする コマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f57cd-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="f57cd-105">Microsoft ダウンロード センターからダウンロードできます (を参照してください[Windows PowerShell を使用してオンライン ビジネスの管理のための Skype には、コンピューターの設定](set-up-your-computer-for-windows-powershell.md)の詳細については) 64 ビット コンピューターでのみサポートされて、このモジュールは、 [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="f57cd-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="f57cd-106">SkypeOnlinePowershell.exe ファイルをダウンロードしてから、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="f57cd-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="f57cd-107">**SkypeOnlinePowershell.exe** ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f57cd-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="f57cd-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span><span class="sxs-lookup"><span data-stu-id="f57cd-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="f57cd-110">[ **Completed the Skype for Business Online, Windows PowerShell Module (Skype for Business Online、Windows PowerShell Module の完了)**] ページで、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f57cd-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="f57cd-p103">セットアップ プログラムが Skype for Business Online Connector モジュール (および **New-CsOnlineSession** コマンドレット) をコンピューターにコピーします。モジュールにアクセスするには、Windows PowerShell セッションを管理者の資格情報で開始してから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f57cd-p103">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="f57cd-p104">このコマンドを Windows PowerShell の開始時に毎回入力しないようにする場合に、そのコマンドを Windows PowerShell プロファイルに追加することができます。これを行うには、Windows PowerShell プロンプトで次のコマンドを入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="f57cd-p104">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="f57cd-115">Notepad が表示されたら、(該当する場合は) 既にプロファイル内にあるコマンドの最下部に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f57cd-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="f57cd-p105">ファイルを保存します。次回の Windows PowerShell の開始時に、Skype for Business Online Connector モジュール が自動的にインポートされます。管理者の資格情報で Windows PowerShell を実行していない場合は、エラー メッセージが表示され、モジュールがロードされないことに留意してください。</span><span class="sxs-lookup"><span data-stu-id="f57cd-p105">Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="f57cd-p106">Skype for Business Online Connector モジュール のインストールに加えて、SkypeOnlinePowershell.exe は、1) Skype for Business Online に対するクライアント認証を処理する Identity Service Client Runtime Library (IDCRL)、2) .NET Framework 4.5、および 3) Microsoft Visual C++ 2012 再頒布可能パッケージ (x64) (バージョン 11.0.50727) という 3 つの追加コンポーネントもインストールします。NET Framework 4.5 は、Windows PowerShell を含む .NET アプリケーションを構築して実行するために使われるインフラストラクチャを提供します。Visual C++ 再頒布可能パッケージは、Microsoft Visual Studio 2012 がインストールされていないコンピューターのために Visual C++ ランタイム コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f57cd-p106">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="f57cd-122">お使いのコンピューターに現在インストールされている Connector モジュールのバージョン番号を検証するには、[ **プログラムと機能** ] を開いて、 **Skype for Business Online、Windows PowerShell Module** のバージョン番号を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f57cd-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f57cd-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f57cd-123">Related topics</span></span>
[<span data-ttu-id="f57cd-124">Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します</span><span class="sxs-lookup"><span data-stu-id="f57cd-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
