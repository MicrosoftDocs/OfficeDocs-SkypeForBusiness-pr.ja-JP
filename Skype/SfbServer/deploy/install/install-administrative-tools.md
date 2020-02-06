---
title: Skype for Business Server で管理ツールをインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '概要: Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790175"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Skype for Business Server で管理ツールをインストールする
 
**概要:** Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 Skype for Business Server の無料トライアルは、次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターからダウンロードしてください。
  
管理ツールには、トポロジビルダーとコントロールパネルが含まれています。 Skype for Business Server でサポートされている Windows OS バージョンを実行している場合は、トポロジまたは64ビット管理ワークステーションの少なくとも1つのサーバーに管理ツールをインストールする必要があります。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 管理ツールのインストール手順は 3/8 です。
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Skype for Business Server 管理ツールをインストールする

Skype for Business Server のインストールメディアには、柔軟なエクスペリエンスが用意されています。 Setup.exe を初めて実行するときにインストールされるツールは、Skype for Business Server 展開ウィザードと Skype for Business Server 管理シェルだけです。 コアコンポーネントと呼ばれるこれら2つのツールを使用することで、インストールプロセスを続行できますが、Skype for Business Server 環境全体の主要機能は提供されません。 展開ウィザードはコア コンポーネントのインストール後に自動で起動されます。 「**管理ツールをインストール**する」というタイトルの展開ウィザードのセクションでは、Skype For Business Server Topology Builder と Skype For Business Server コントロールパネルをインストールします。
  
> [!IMPORTANT]
> すべての Skype for Business Server 環境には、管理ツールがインストールされているサーバーが少なくとも1つ必要です。 
  
**管理ツールのインストール**手順に関するビデオを見てください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>展開ウィザードから Skype for Business Server 管理ツールをインストールする

1. Skype for Business Server インストールメディアを挿入します。 セットアップが自動で開始されない場合は、[**セットアップ**] をダブルクリックします。
    
2. インストール メディアを実行するには、Microsoft Visual C++ が必要です。インストールするかどうかをたずねるダイアログ ボックスが表示されたら、[**はい**] をクリックします。
    
3. Skype for Business Server の新機能であるスマートセットアップを使用すると、インターネットに接続して、インストールプロセス中に更新プログラムを確認することができます。 これにより、インストール時の製品に最新の更新プログラムを確実に適用できるため、作業がしやすくなります。 [**インストール**] をクリックしてインストールを開始します。
    
4. 使用許諾契約書の内容をよく読んでください。同意する場合は [**使用許諾契約書に同意します**] を選択し、[**OK**] をクリックします。
    
5. Skype for Business Server のコアコンポーネントはサーバーにインストールされます。 
    
    コア コンポーネントは、図に示されている次のコンポーネントで構成されています。
    
    ![アプリの画面のコア コンポーネント](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype For Business Server Deployment ウィザード**Skype for Business Server のさまざまなコンポーネントをインストールするための起動パッドを提供する展開プログラム。
    
   - **Skype For Business Server 管理シェル**Skype for Business Server の管理を可能にする事前構成済み PowerShell プログラム。
    
     コアコンポーネントのインストールが完了すると、図に示すように、Skype for Business Server Deployment ウィザードが自動的に起動します。 
    
     ![Skype for Business Server 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. コアコンポーネントに加えて、環境内の少なくとも1台のサーバーに Skype for Business Server Topology Builder と Skype for Business Server コントロールパネルをインストールする必要があります。 展開ウィザードの [**管理ツールのインストール**] をクリックします。
    
7. [**次へ**] をクリックして、インストールを開始します。
    
8. インストールが完了したら、[**完了**] をクリックします。これで、管理ツールがサーバーに追加されました。図に例を示します。
    
    ![Skype for Business Server 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype For Business Server トポロジビルダー**トポロジを構築、展開、管理するために使用されるプログラム。
    
   - **Skype For Business Server コントロールパネル**インストールを管理するために使用されるプログラム。
    

