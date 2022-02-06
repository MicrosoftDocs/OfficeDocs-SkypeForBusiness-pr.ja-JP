---
title: 管理ツールをインストールSkype for Business Server
ms.reviewer: null
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
ms.custom: null
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '概要: インストールに必要な管理ツールをインストールする方法について説明Skype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードしますhttps://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
---

# <a name="install-administrative-tools-in-skype-for-business-server"></a>管理ツールをインストールSkype for Business Server
 
**概要:** アプリケーションのインストールに必要な管理ツールをインストールするSkype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。 管理ツールは、トポロジ内の少なくとも 1 台のサーバーまたは Windows OS バージョンを実行する 64 ビット管理ワークステーションにインストールする必要があります。Skype for Business Server。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示されている手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 管理ツールのインストールは、手順 3 / 8 です。
  
![概要図。](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>管理Skype for Business Serverインストールする

ユーザーのインストール メディアはSkype for Business Serverなエクスペリエンスを提供します。 最初にインストールをSetup.exe、インストールされているツールは、展開ウィザードSkype for Business Server管理シェルSkype for Business Serverのみです。 コア コンポーネントと呼ばれるこれら 2 つのツールを使用すると、インストール プロセスを続行できますが、これらのツールは、環境全体の主要な機能Skype for Business Serverではありません。 コア コンポーネントをインストールすると、展開ウィザードが自動的に起動します。 「管理ツールのインストール」というタイトルの展開ウィザードのセクション **では**、Skype for Business Serverビルダーとコントロール Skype for Business Serverインストールします。
  
> [!IMPORTANT]
> すべてのSkype for Business Server管理ツールがインストールされているサーバーが少なくとも 1 つ必要です。 
  
管理ツールのインストールに関する **ビデオの手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>展開Skype for Business Serverから管理ツールをインストールする

1. インストール メディアSkype for Business Server挿入します。 セットアップが自動的に開始されない場合は、[セットアップ] をダブルクリック **します**。
    
2. インストール メディアを実行するには、Microsoft Visual C++が必要です。 インストールを求めるダイアログ ボックスが表示されます。 [**はい**] をクリックします。
    
3. 新しい機能である Smart Setup をSkype for Business Server、インターネットに接続して、インストール プロセス中に更新プログラムを確認できます。 これにより、インストール時に製品に対する最新の更新プログラムが確実に提供され、より良いエクスペリエンスが提供されます。 **[インストール]** をクリックして、インストールを開始します。
    
4. 使用許諾契約書を慎重に確認し、同意する場合は、[使用許諾契約書の条項に同意する] を **選択** し、[OK] をクリック **します**。
    
5. サーバー Skype for Business Serverコア コンポーネントがインストールされます。 
    
    図に示すように、コア コンポーネントは次のコンポーネントで構成されます。
    
    ![[アプリ] 画面の [コア コンポーネント]](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server展開ウィザード** の各種コンポーネントをインストールする起動パッドを提供する展開Skype for Business Server。
    
   - **Skype for Business Server管理シェル** の管理を可能にする事前構成済みの PowerShell プログラムSkype for Business Server。
    
     コア コンポーネントのインストールが完了すると、図Skype for Business Server展開ウィザードが自動的に起動します。 
    
     ![Skype for Business Server展開ウィザード。](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. コア コンポーネントに加えて、環境内の少なくとも 1 Skype for Business Server サーバーに Skype for Business Server および Skype for Business Server コントロール パネルをインストールする必要があります。 展開 **ウィザードで [管理ツール** のインストール] をクリックします。
    
7. [**次へ**] をクリックして、インストールを開始します。
    
8. インストールが完了したら、[完了] を **クリックします**。 図に示すように、管理ツールがサーバーに追加されました。
    
    ![Skype for Business Server管理ツール。](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server トポロジ ビルダー** トポロジの構築、展開、および管理に使用されるプログラム。
    
   - **Skype for Business Server コントロール パネル** インストールの管理に使用されるプログラム。
    

