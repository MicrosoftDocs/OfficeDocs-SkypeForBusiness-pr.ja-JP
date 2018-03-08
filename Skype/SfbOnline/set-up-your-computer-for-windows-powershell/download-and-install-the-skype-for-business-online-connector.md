---
title: "ダウンロードして、Skype for Business Online コネクタ モジュールをインストールします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: "ダウンロード、インストール、および Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Skype for Business Online コネクタを使用します。 "
ms.openlocfilehash: e95b65d62434a6ea7a52714536b1b11d47f08a8c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="f18dd-103">ダウンロードして、Skype for Business Online コネクタ モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f18dd-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="f18dd-p101">Skype for Business Online コネクタ モジュールでは、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができる**新しい CsOnlineSession**コマンドレットが含まれています。このモジュールでは、「 [skype for Business Online 管理を Windows PowerShell を使用して、コンピューター設定する](set-up-your-computer-for-windows-powershell.md)詳細については)、64 ビット コンピューター以外ではは、 [https:// に Microsoft ダウンロード センターからダウンロードできます。www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)します。SkypeOnlinePowershell.exe ファイルをダウンロードしてから、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f18dd-p101">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="f18dd-107">**SkypeOnlinePowershell.exe**ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f18dd-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="f18dd-p102">Skype for Business Online では、Windows PowerShell のセットアップ ウィザードの**Microsoft ソフトウェア ライセンス条項**] ページは、**使用許諾契約書の条項に同意します**] を選択し、[**インストール**] をクリックします。場合は、 **[ユーザー アカウント制御**] ダイアログ ボックスが表示されたら、 **[はい**インストールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f18dd-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="f18dd-110">[ **Skype for Business Online、Windows PowerShell モジュールの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f18dd-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="f18dd-p103">セットアップ プログラムは、Skype for Business Online コネクタ モジュール (と**新規 CsOnlineSession**コマンドレット) を自分のコンピューターにコピーします。モジュールにアクセスするには、管理者の資格情報は、[Windows PowerShell セッションを開始し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f18dd-p103">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="f18dd-p104">Windows PowerShell を起動するたびに、このコマンドを入力しない場合は、Windows PowerShell の自分のプロファイルにコマンドを追加できます。そのため、Windows PowerShell のプロンプトで、次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f18dd-p104">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="f18dd-115">メモ帳が表示されたら、(設定されている場合) のプロファイルに存在するコマンドの下部に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f18dd-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="f18dd-p105">ファイルを保存します。次に、Windows PowerShell を起動したとき、Skype for Business Online コネクタ モジュールが自動的にインポートされます。エラー メッセージが表示されますとなるモジュールを読み込むことができませんが、Windows PowerShell が管理者の資格情報で実行されていない場合。</span><span class="sxs-lookup"><span data-stu-id="f18dd-p105">Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="f18dd-p106">Skype for Business Online コネクタ モジュールをインストールするには、SkypeOnlinePowershell.exe もインストールが 3 つの他のコンポーネント: 1)、身元サービス クライアント ランタイム ライブラリ (IDCRL)、skype for Business クライアントの認証を処理します。オンラインです。2) .NET framework 4.5 です。3)、Microsoft Visual C++ 2012 再頒布可能コンポーネント (x64) パッケージ (バージョン 11.0.50727)。.NET framework 4.5 では、作成したり、Windows PowerShell を含む、.NET アプリケーションを実行するために使用するインフラストラクチャを提供します。Microsoft Visual Studio 2012 がインストールされていないコンピューターの Visual C ランタイム コンポーネントを視覚的な C++ 再頒布可能コンポーネントにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f18dd-p106">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="f18dd-122">現在コンピューターにインストールされているコネクタ モジュールのバージョン番号を確認するには、[コントロール パネルを開きます**プログラムと機能**] を開く、 **Skype for Business Online、Windows PowerShell モジュール**のバージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="f18dd-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f18dd-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f18dd-123">Related topics</span></span>
[<span data-ttu-id="f18dd-124">Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="f18dd-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
