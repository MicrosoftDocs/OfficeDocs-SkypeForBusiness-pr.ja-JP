---
title: Skype for Business Server に管理ツールをインストールする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812107"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Skype for Business Server に管理ツールをインストールする
 
**概要:** Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。 管理ツールは、トポロジ内の少なくとも 1 台のサーバー、または Skype for Business Server でサポートされている Windows OS バージョンを実行している 64 ビットの管理ワークステーションにインストールする必要があります。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。 管理ツールのインストールは、手順 3/8 です。
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Skype for Business Server 管理ツールのインストール

Skype for Business Server のインストール メディアは、柔軟なエクスペリエンスを提供します。 最初にインストールSetup.exeインストールされるツールは、Skype for Business Server 展開ウィザードと Skype for Business Server 管理シェルのみです。 コア コンポーネントと呼ばれるこれら 2 つのツールを使用すると、インストール プロセスを続行できますが、Skype for Business Server 環境全体の主要な機能は提供されません。 コア コンポーネントをインストールすると、展開ウィザードが自動的に起動します。 展開ウィザードの 「管理ツールのインストール」というタイトルのセクションでは、Skype for Business Server トポロジ ビルダーと Skype for Business Server コントロール パネルをインストールします。
  
> [!IMPORTANT]
> すべての Skype for Business Server 環境には、管理ツールがインストールされたサーバーが少なくとも 1 つ必要です。 
  
管理ツールのインストールに関する **ビデオの手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>展開ウィザードから Skype for Business Server 管理ツールをインストールする

1. Skype for Business Server インストール メディアを挿入します。 セットアップが自動的に開始されない場合は、[セットアップ] をダブルクリック **します**。
    
2. インストール メディアを実行するには、Microsoft Visual C++ が必要です。 インストールを求めるダイアログ ボックスが表示されます。 [**はい**] をクリックします。
    
3. Skype for Business Server の新機能であるスマート セットアップを使用すると、インターネットに接続してインストール プロセス中に更新プログラムを確認できます。 これにより、インストール時に製品に対する最新の更新プログラムが確実に適用され、エクスペリエンスが向上します。 **[インストール]** をクリックして、インストールを開始します。
    
4. 使用許諾契約書を慎重に確認し、同意する場合は、[使用許諾契約書に同意します] を選択し **、[OK]** をクリックします。
    
5. Skype for Business Server コア コンポーネントがサーバーにインストールされます。 
    
    図に示すように、コア コンポーネントは次の要素で構成されます。
    
    ![[アプリ] 画面のコア コンポーネント。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server 展開ウィザード** Skype for Business Server のさまざまなコンポーネントをインストールする起動パッドを提供する展開プログラム。
    
   - **Skype for Business Server 管理シェル** Skype for Business Server の管理を可能にする事前構成済みの PowerShell プログラム。
    
     コア コンポーネントのインストールが完了すると、次の図に示すように、Skype for Business Server 展開ウィザードが自動的に起動します。 
    
     ![Skype for Business Server 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. コア コンポーネントに加えて、環境内の少なくとも 1 つのサーバーに Skype for Business Server トポロジ ビルダーと Skype for Business Server コントロール パネルをインストールする必要があります。 展開 **ウィザードで [管理ツールの** インストール] をクリックします。
    
7. [**次へ**] をクリックして、インストールを開始します。
    
8. インストールが完了したら、[完了] をクリック **します**。 次の図に示すように、管理ツールがサーバーに追加されます。
    
    ![Skype for Business Server 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server トポロジ ビルダー** トポロジの構築、展開、および管理に使用するプログラム。
    
   - **Skype for Business Server コントロール パネル** インストールを管理するために使用するプログラム。
    

