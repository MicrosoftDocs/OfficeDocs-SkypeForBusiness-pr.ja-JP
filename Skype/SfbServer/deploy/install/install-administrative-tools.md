---
title: Skype for Business Serverに管理ツールをインストールする
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '概要: Skype for Business Serverのインストールに必要な管理ツールをインストールする方法について説明します。'
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860528"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Skype for Business Serverに管理ツールをインストールする
 
**概要：** Skype for Business Serverのインストールに必要な管理ツールをインストールする方法について説明します。
  
管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。 管理ツールは、トポロジ内の少なくとも 1 つのサーバー、またはSkype for Business ServerでサポートされているWindows OS バージョンを実行している 64 ビット管理ワークステーションにインストールする必要があります。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示すように、手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 管理ツールのインストールは、手順 3/ 8 です。
  
![概要図。](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>管理ツールSkype for Business Serverインストールする

Skype for Business Server用のインストール メディアは、柔軟なエクスペリエンスを提供します。 Setup.exeを初めて実行するときにインストールされるツールは、Skype for Business Server 展開ウィザードと Skype for Business Server管理シェルだけです。 コア コンポーネントと呼ばれるこの 2 つのツールを使用すると、インストール プロセスを続行できますが、Skype for Business Server環境全体の主な機能は提供されません。 コア コンポーネントをインストールすると、展開ウィザードが自動的に起動します。 [**管理ツールのインストール**] というタイトルの展開ウィザードのセクションでは、トポロジ ビルダーとSkype for Business Server コントロール パネルSkype for Business Serverインストールされます。
  
> [!IMPORTANT]
> すべてのSkype for Business Server環境には、管理ツールがインストールされた少なくとも 1 つのサーバーが必要です。 
  
**管理ツールのインストール** に関するビデオの手順をご覧ください。
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>展開ウィザードから管理ツールSkype for Business Serverインストールする

1. Skype for Business Serverインストール メディアを挿入します。 セットアップが自動的に開始されない場合は、[ **セットアップ**] をダブルクリックします。
    
2. インストール メディアを実行するには、Microsoft Visual C++が必要です。 インストールするかどうかを確認するダイアログ ボックスが表示されます。 [**はい**] をクリックします。
    
3. Skype for Business Serverの新機能である Smart Setup を使用すると、インターネットに接続して、インストール プロセス中に更新プログラムを確認できます。 これにより、インストール時に製品に対する最新の更新プログラムがあることを確認することで、エクスペリエンスが向上します。 **[インストール]** をクリックして、インストールを開始します。
    
4. 使用許諾契約書を慎重に確認し、同意する場合 **は、使用許諾契約書の条項に同意する** を選択し、[OK] をクリック **します**。
    
5. Skype for Business Serverコア コンポーネントがサーバーにインストールされます。 
    
    図に示すように、コア コンポーネントは次で構成されます。
    
    ![[アプリのコア コンポーネント] 画面。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server 展開ウィザード** Skype for Business Serverのさまざまなコンポーネントをインストールするための起動パッドを提供する展開プログラム。
    
   - **Skype for Business Server 管理シェル** Skype for Business Serverの管理を可能にする事前構成済みの PowerShell プログラム。
    
     コア コンポーネントのインストールが完了すると、図に示すように、Skype for Business Server展開ウィザードが自動的に起動します。 
    
     ![Skype for Business Server展開ウィザード。](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. コア コンポーネントに加えて、Skype for Business Server トポロジ ビルダーとSkype for Business Server コントロール パネルを環境内の少なくとも 1 つのサーバーにインストールする必要もあります。 展開ウィザードで [ **管理ツールのインストール** ] をクリックします。
    
7. [**次へ**] をクリックして、インストールを開始します。
    
8. インストールが完了したら、[完了] をクリック **します**。 次の図に示すように、管理ツールがサーバーに追加されました。
    
    ![Skype for Business Server管理ツール。](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server トポロジ ビルダー** トポロジのビルド、デプロイ、および管理に使用されるプログラム。
    
   - **Skype for Business Server コントロール パネル** インストールの管理に使用されるプログラム。
    

