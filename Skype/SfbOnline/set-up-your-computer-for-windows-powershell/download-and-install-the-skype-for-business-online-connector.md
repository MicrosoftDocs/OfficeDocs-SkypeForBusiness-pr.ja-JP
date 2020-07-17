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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: 8c5068c221c46f7be0d9d97c1c3d515ae244b316
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085703"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="ea462-103">Skype for Business Online Connector モジュールをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="ea462-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="ea462-104">最新の[Teams powershell パブリックプレビューリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)は、Skype For Business Online Connector と統合されており、teams PowerShell 管理用の1つのモジュールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="ea462-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="ea462-105">[] Skype for Business Online Connector モジュール には、 **New-CsOnlineSession** Windows PowerShell に接続するリモート Skype for Business Online セッションを作成できるようにする コマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea462-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="ea462-106">このモジュールは、64ビットのコンピューターでのみサポートされます (詳細については、「 [Windows PowerShell を使用して Skype For Business Online 管理用にコンピューターを設定](set-up-your-computer-for-windows-powershell.md)する」を参照してください)。 Microsoft ダウンロードセンターからダウンロードでき [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) ます。</span><span class="sxs-lookup"><span data-stu-id="ea462-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="ea462-107">SkypeOnlinePowershell.exe ファイルをダウンロードしてから、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="ea462-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="ea462-108">**SkypeOnlinePowershell.exe** ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea462-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="ea462-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span><span class="sxs-lookup"><span data-stu-id="ea462-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="ea462-111">[ **Completed the Skype for Business Online, Windows PowerShell Module (Skype for Business Online、Windows PowerShell Module の完了)**] ページで、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea462-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="ea462-p103">セットアップ プログラムが Skype for Business Online Connector モジュール (および **New-CsOnlineSession** コマンドレット) をコンピューターにコピーします。モジュールにアクセスするには、Windows PowerShell セッションを管理者の資格情報で開始してから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea462-p103">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="ea462-p104">このコマンドを Windows PowerShell の開始時に毎回入力しないようにする場合に、そのコマンドを Windows PowerShell プロファイルに追加することができます。これを行うには、Windows PowerShell プロンプトで次のコマンドを入力してから ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="ea462-p104">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="ea462-116">Notepad が表示されたら、(該当する場合は) 既にプロファイル内にあるコマンドの最下部に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea462-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="ea462-p105">ファイルを保存します。次回の Windows PowerShell の開始時に、Skype for Business Online Connector モジュール が自動的にインポートされます。管理者の資格情報で Windows PowerShell を実行していない場合は、エラー メッセージが表示され、モジュールがロードされないことに留意してください。</span><span class="sxs-lookup"><span data-stu-id="ea462-p105">Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="ea462-p106">Skype for Business Online Connector モジュール のインストールに加えて、SkypeOnlinePowershell.exe は、1) Skype for Business Online に対するクライアント認証を処理する Identity Service Client Runtime Library (IDCRL)、2) .NET Framework 4.5、および 3) Microsoft Visual C++ 2012 再頒布可能パッケージ (x64) (バージョン 11.0.50727) という 3 つの追加コンポーネントもインストールします。NET Framework 4.5 は、Windows PowerShell を含む .NET アプリケーションを構築して実行するために使われるインフラストラクチャを提供します。Visual C++ 再頒布可能パッケージは、Microsoft Visual Studio 2012 がインストールされていないコンピューターのために Visual C++ ランタイム コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ea462-p106">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="ea462-123">お使いのコンピューターに現在インストールされている Connector モジュールのバージョン番号を検証するには、[ **プログラムと機能** ] を開いて、 **Skype for Business Online、Windows PowerShell Module** のバージョン番号を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ea462-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ea462-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea462-124">Related topics</span></span>
[<span data-ttu-id="ea462-125">Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ea462-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
