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
description: '概要: ビジネス サーバー 2015 の Skype のインストールに必要な管理ツールをインストールする方法を説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 への管理ツールのインストール
 
**の概要:**ビジネス サーバー 2015 の Skype のインストールに必要な管理ツールをインストールする方法について説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
管理ツールには、トポロジ ビルダーおよびコントロール パネルが含まれます。 トポロジまたは Skype ビジネス サーバーのサポートされている Windows のオペレーティング システムのバージョンを実行している 64 ビットの管理ワークステーションで少なくとも 1 つのサーバーの管理ツールをインストールしなければなりません。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。 8 のステップ 3 は、管理ツールをインストールします。
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Skype をビジネス サーバー 2015 の管理ツールをインストールします。

ビジネス サーバー 2015 の Skype のインストール メディアでは、柔軟性の高いエクスペリエンスを提供します。 最初に Setup.exe を実行するときのみのツールがインストールされているビジネス サーバーの展開ウィザードの Skype とビジネスのサーバー管理シェルの Skype コア コンポーネントと呼ばれるこれらの 2 つのツールを使用して、インストール プロセスを続行することができますが、ビジネス サーバー環境の全体的な Skype の主要な機能は提供されません。 展開ウィザードはコア コンポーネントのインストール後に自動で起動されます。 **管理ツールのインストール**を [展開ウィザード] のセクションでは、ビジネス サーバーのコントロール パネルのビジネス サーバー トポロジ ビルダーと Skype の Skype をインストールします。
  
> [!IMPORTANT]
> ビジネス サーバー環境のすべての Skype がインストールされている管理ツールを使用して、少なくとも 1 つのサーバーが必要です。 
  
**管理ツールのインストール**手順に関するビデオを見てください。
  
![ブラウザーがビデオをサポートしていません。Microsoft Silverlight、Adobe Flash Player、または Internet Explorer 9 をインストールしてください。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>展開ウィザードの [管理ツールのビジネス サーバー 2015 の Skype をインストールします。

1. Skype ビジネス サーバー 2015 のインストール メディアを挿入します。 セットアップが自動で開始されない場合は、[**セットアップ**] をダブルクリックします。
    
2. インストール メディアを実行するには、Microsoft Visual C++ が必要です。インストールするかどうかをたずねるダイアログ ボックスが表示されたら、[**はい**] をクリックします。
    
3. スマート セットアップ、Skype のビジネス サーバー 2015 年の新機能を使用して、インストール処理中に更新プログラムを確認するのにはインターネットに接続できます。 これにより、インストール時の製品に最新の更新プログラムを確実に適用できるため、作業がしやすくなります。 [**インストール**] をクリックしてインストールを開始します。
    
4. 使用許諾契約書の内容をよく読んでください。同意する場合は [**使用許諾契約書に同意します**] を選択し、[**OK**] をクリックします。
    
5. ビジネス サーバー 2015 のコア ・ コンポーネントの Skype は、サーバーにインストールされます。 
    
    コア コンポーネントは、図に示されている次のコンポーネントで構成されています。
    
    ![アプリの画面のコア コンポーネント](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **ビジネス サーバーの展開ウィザードが 2015年の Skype**ビジネス サーバー 2015 の Skype のさまざまなコンポーネントをインストールするための起動パッドを提供する導入プログラムです。
    
  - **Skype ビジネス サーバー 2015年管理シェルには**ビジネス サーバー 2015 の Skype の管理を可能にする PowerShell の事前に構成されたプログラムです。
    
    コア ・ コンポーネントのインストールが完了した後、ビジネス サーバー 2015 の展開ウィザードの Skype が自動的に起動、図に示すようにします。 
    
    ![Skype for Business Server 2015 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. コア コンポーネントに加えて、環境内の少なくとも 1 つのサーバーで、ビジネス サーバー 2015 のコントロール パネルのビジネス サーバー 2015 のトポロジ ビルダーと Skype の Skype をインストールする必要がも。 展開ウィザードの [**管理ツールのインストール**] をクリックします。
    
7. [**次へ**] をクリックして、インストールを開始します。
    
8. インストールが完了したら、[**完了**] をクリックします。これで、管理ツールがサーバーに追加されました。図に例を示します。
    
    ![Skype for Business Server 2015 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype ビジネス サーバー 2015年トポロジ ビルダーの**プログラムをビルド、配置、およびトポロジを管理するために使用します。
    
   - **Skype ビジネス サーバー 2015年コントロール パネルの**プログラムのインストールを管理するために使用します。
    

