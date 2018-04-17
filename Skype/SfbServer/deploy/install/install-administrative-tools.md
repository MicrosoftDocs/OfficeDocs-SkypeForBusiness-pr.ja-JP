---
title: Skype for Business Server 2015 への管理ツールのインストール
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Summary: Learn how to install the administrative tools required for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: c0d6b4a2ad41fbca4c89e6095a34eabf08e191ee
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 への管理ツールのインストール
 
**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
The administrative tools include Topology Builder and the Control Panel. The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server. 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。 Installing the administrative tools is step 3 of 8.
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Install Skype for Business Server 2015 administrative tools

The installation media for Skype for Business Server 2015 provides a flexible experience. When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell. By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment. 展開ウィザードはコア コンポーネントのインストール後に自動で起動されます。 The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.
  
> [!IMPORTANT]
> Every Skype for Business Server environment must have at least one server with the administrative tools installed. 
  
**管理ツールのインストール**手順に関するビデオを見てください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>Install Skype for Business Server 2015 administrative tools from the Deployment Wizard

1. Insert the Skype for Business Server 2015 installation media. セットアップが自動で開始されない場合は、[**セットアップ**] をダブルクリックします。
    
2. インストール メディアを実行するには、Microsoft Visual C++ が必要です。インストールするかどうかをたずねるダイアログ ボックスが表示されたら、[**はい**] をクリックします。
    
3. By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process. これにより、インストール時の製品に最新の更新プログラムを確実に適用できるため、作業がしやすくなります。 [**インストール**] をクリックしてインストールを開始します。
    
4. 使用許諾契約書の内容をよく読んでください。同意する場合は [**使用許諾契約書に同意します**] を選択し、[**OK**] をクリックします。
    
5. The Skype for Business Server 2015 Core Components will be installed on the server. 
    
    コア コンポーネントは、図に示されている次のコンポーネントで構成されています。
    
    ![アプリの画面のコア コンポーネント](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.
    
  - **Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.
    
    Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure. 
    
    ![Skype for Business Server 2015 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment. 展開ウィザードの [**管理ツールのインストール**] をクリックします。
    
7. [**次へ**] をクリックして、インストールを開始します。
    
8. インストールが完了したら、[**完了**] をクリックします。これで、管理ツールがサーバーに追加されました。図に例を示します。
    
    ![Skype for Business Server 2015 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.
    
   - **Skype for Business Server 2015 Control Panel** A program used to administer the installation.
    

