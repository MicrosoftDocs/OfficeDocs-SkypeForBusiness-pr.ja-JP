---
title: Skype for Business Server のインストール
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
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '概要: 環境のインストールを準備する方法についてSkype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードしますhttps://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 8b129f164cb2650615cf20084f0617da419e4aeb
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386256"
---
# <a name="install-skype-for-business-server"></a>Skype for Business Server のインストール
 
**概要:** アプリケーションのインストール用に環境を準備する方法についてSkype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
この記事では、アプリケーションのインストール例について説明Skype for Business Server。 この記事では、完全なインストールを実行するために必要なすべての手順をSkype for Business Serverではありません。 目標は、基本的な meet-and-share 機能を含む、狭く定義されたトポロジでプロシージャの例を提供します。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>アプリケーションのインストール プロセスのSkype for Business Server

アプリケーションのインストールにはSkype for Business Serverさまざまな手順が含まれます。 環境で実行するために必要Skype for Business Server手順は、環境の詳細によって異なります。 たとえば、DNS に Windowsを使用している場合は、DNS エントリを追加する手順の例を利用できます。 DNS に別のシステムを使用する場合は、特定の DNS システムの手順に従う必要があります。 これは、このセクションの多くの手順に当てはまる。
  
Skype for Business Serverは、Standard EditionおよびEnterprise Edition。 主な違いは、Standard Editionに含まれる高可用性機能をサポートしていない点Enterprise Edition。 
  
Skype for Business Serverは高度な製品であり、正確なインストール プロセスは特定の状況に大きな依存します。 このセクションでは、製品をインストールするための一般的な手順について説明します。 ただし、各手順は、環境や計画の決定によって異なる場合があります。 たとえば、小規模な組織では、Skype for Business Server Standard Edition を実行するサーバーが適切ですが、大規模な多国籍組織では、製品専用の世界中の場所に 50 台のサーバーがある場合があります。
  
> [!NOTE]
> 最新の累積的な更新プログラムの詳細については、「更新[プログラムの更新プログラム」を参照Skype for Business Server](https://support.microsoft.com/kb/3061064)。 CU1 パッチをインストールした後、管理者はコマンドレットを実行する必要  `Update-CsAdminRole` があります。 このコマンドレットは、リモート PowerShell を使用して新しい GCP コマンドレットにアクセスするために必要です。
  
> [!IMPORTANT]
> このセクションの手順は、狭く定義された一連の要件を使用する例として機能し、特定の決定が既に行われたと仮定します。 インストールする必要がある実際の手順Skype for Business Server大きな違いがあります。 このセクションの手順は、すべての環境にインストールする手順の詳細なガイドとしてではなく、例Skype for Business Server使用します。 
  
初めてSkype for Business Server実行するには、8 つの主要な手順が含まれます。 このセクションの例の手順は、このセクションのインストールに必要な唯一の手順Skype for Business Server。 次の 8 つの手順は、プロセス全体をよりよく理解し、基本的な作業環境を立ち上げ、実行するのに役立つ例です。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示されている手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 8 つの手順は次のとおりです。
  
![インストール プロセスの概要。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [サーバーの前提条件をインストールSkype for Business Server](install-prerequisites.md): トポロジを構成するすべてのサーバーに前提条件をSkype for Business Serverします。 前提条件がすべての役割で同じではない点に注意してください。 たとえば、フロントエンドの役割を提供するサーバーには一連の前提条件が含まれています。ディレクターの役割を提供するサーバーの前提条件は異なります。 詳細については、前提条件の計画に関するドキュメントを参照してください。
    
- [[ファイル共有を作成する](create-a-file-share.md)] Skype for Business Serverトポロジ全体でサーバーで使用するファイル共有をSkype for Business Serverします。
    
- [[管理ツールのインストール]](install-administrative-tools.md) Skype for Business Server: 管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。 管理ツールは、トポロジ内の少なくとも 1 つのサーバー、または Skype for Business Server でサポートされている Windows OS バージョンを実行する 64 ビット管理ワークステーションにインストールする必要があります。
    
- [Active Directory を準備Skype for Business Server](prepare-active-directory.md) : Skype for Business Server Active Directory と密接に動作します。 Active Directory ドメインを準備して、このドメインをSkype for Business Server。 これを行うには、展開ウィザードを使用して、ドメインに対して 1 回だけ実行します。 これは、プロセスによってグループが作成され、ドメインが変更され、1 回だけ行う必要があるためです。
    
- [ユーザーの DNS](create-dns-records.md) レコードSkype for Business Server作成する : Skype for Business Serverを正しく動作するには、多数の DNS 設定が必要です。 これは、クライアントがサービスにアクセスする方法を知り、サーバーが互いについて知っているのです。 これらの設定は、DNS エントリを割り当てるとドメイン全体で使用できるので、展開ごとに 1 回だけ完了する必要があります。
    
- [Skype for Business Server で](create-and-publish-new-topology.md)新しいトポロジを作成して発行する : トポロジ内の各サーバーに Skype for Business Server システムをインストールする前に、トポロジを作成して公開する必要があります。 トポロジを発行する場合は、トポロジ情報を中央管理ストア データベースに読み込む必要があります。 これがサーバー プールEnterprise Edition、新しいトポロジを初めて公開する際に、サーバーの全体管理ストア データベースを作成します。 この設定がStandard Editionトポロジを公開する前に、展開ウィザードから [最初のサーバー Standard Edition準備] プロセスを実行する必要があります。 これにより、Standard Edition Edition インスタンスSQL Server Expressサーバーの全体管理ストアを作成することで、サーバーの準備が整います。
    
- [トポロジSkype for Business Server](install-skype-for-business-server.md)サーバーに Skype for Business Server をインストールする : トポロジが中央管理ストアに読み込まれ、Active Directory でどのサーバーがどの役割を実行するのかを確認したら、トポロジ内の各サーバーに Skype for Business Server システムをインストールする必要があります。
    
- [Skype for Business Server で](verify-the-topology.md)トポロジを確認する: トポロジが公開され、トポロジ内の各サーバーに Skype for Business Server システム コンポーネントがインストールされた後、トポロジが正常に動作している状態を確認する準備が整います。 これには、構成がすべての Active Directory サーバーに伝達され、ドメイン全体がドメイン内で使用可能Skype for Business確認できます。
    

