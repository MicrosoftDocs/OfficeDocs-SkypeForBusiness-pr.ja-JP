---
title: Skype for Business Server 2015 のインストール
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
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '概要: ビジネス サーバー 2015 の Skype のインストール環境を準備する方法を説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 6cb30ef44411705d16ce9175e92a9204d8b09766
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="install-skype-for-business-server-2015"></a>Skype for Business Server 2015 のインストール
 
**の概要:**ビジネス サーバー 2015 の Skype のインストール環境を準備する方法について説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
この資料の手順を Skype のインストール例ビジネス サーバー 2015 のです。 この資料は、ビジネスのサーバーのインストールの完全 Skype を実行する必要の手順のすべてをカバーするしません。 基本的な会議および共有機能を含む、狭義のトポロジの手順例を提供することを目的としています。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype のインストール ・ プロセスの概要

Skype ビジネス サーバーのインストールには、多くの異なる手順が含まれています。 環境内で実行されているビジネス サーバーの Skype を取得する必要があります手順は、お客様の環境の詳細によって異なります。 たとえば、DNS として Windows Server を使用する場合は、DNS エントリを追加する手順例が役に立ちます。 DNS として別のシステムを使用する場合は、特定の DNS システムの手順に従う必要があります。 これは、このセクションの多くの手順に当てはまります。
  
ビジネス サーバー 2015 の Skype は、Standard Edition および Enterprise Edition で使用できます。 2 つのエディションの主な違いは、Enterprise Edition には含まれている高可用性機能を Standard Edition ではサポートしていない点です。 
  
ビジネス サーバー用の Skype は、高度な製品では、および正確なインストール プロセスが、特定の状況で多く依存します。 このセクションでは、この製品をインストールするための一般的な手順について順を追って説明します。 ただし、各手順は環境や計画事項によって異なる場合があります。 などの小規模な組織の 1 つのサーバーでは、Skype ビジネス サーバー 2015 の Standard Edition を実行している場合があります適切な大規模な多国籍組織では、専用の製品を世界各地に 50 台のサーバーがあります。
  
> [!NOTE]
> 最新の累積的な更新プログラムについては、[ビジネス サーバー 2015 の Skype 用の更新プログラム](https://support.microsoft.com/en-us/kb/3061064)を参照してください。 CU1 の修正プログラムをインストールした後は、管理者が実行する必要が、`Update-CsAdminRole`コマンドレットです。 このコマンドレットは、リモート PowerShell 経由で新しい GCP コマンドレットにアクセスするために必要です。
  
> [!IMPORTANT]
> このセクションの手順は、狭義に定義された一連の要件を使用する例を示すことを目的としており、何らかの具体的な決定が既に行われているものと仮定しています。 ビジネス サーバー用の Skype をインストールする必要があります実際の手順が大きく異なる可能性がありますがあります。 プロシージャを使用、このセクションの唯一の例として、ステップ バイ ステップ ガイドではなくビジネス サーバーのすべての環境で Skype をインストールするため。 
  
Skype ビジネス サーバーにし、最初に実行している 8 つの主な手順が含まれます。 このセクションの例の手順は、Skype をビジネスのサーバーのインストールに必要な唯一の手順ではないことを理解する必要があります。 次の 8 つの手順は、全体的なプロセスの理解を深め、基本的な作業環境を立ち上げるための一例にすぎません。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。 8 つの手順は次のとおりです。
  
![インストール プロセスの概要](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Skype サーバー 2015 のビジネスのための前提条件のインストール](install-prerequisites.md): ビジネス サーバー トポロジの Skype を構成するすべてのサーバー上の前提条件をインストールします。 前提条件はどの役割でも同じというわけではない点に注意してください。 たとえば、フロントエンドの役割を提供するサーバーとディレクターの役割を提供するサーバーとでは、前提条件となる機能のセットが異なります。 詳細については、前提条件の計画ドキュメントを参照してください。
    
- [ビジネス サーバー 2015 の Skype でファイル共有を作成](create-a-file-share.md)します。 ビジネス サーバー トポロジの場合、Skype 全体のサーバーによって使用されるファイル共有を作成します。
    
- [ビジネス サーバー 2015 の Skype での管理ツールのインストール](install-administrative-tools.md): トポロジ ビルダーおよびコントロール パネルの [管理ツールが含まれます。 トポロジまたは Skype ビジネス サーバーのサポートされている Windows のオペレーティング システムのバージョンを実行している 64 ビットの管理ワークステーションで少なくとも 1 つのサーバー上で管理ツールをインストールする必要があります。
    
- [ビジネス サーバー 2015 の Skype 用の Active Directory の準備](prepare-active-directory.md): Skype のビジネス サーバーは Active Directory と密接します。 Skype でビジネスのサーバーを使用する Active Directory ドメインを準備する必要があります。 このプロセスは展開ウィザードによって実行され、ドメインに対して 1 回のみ行います。 これは、プロセスによってグループの作成とドメインの変更が実行されるため、1 回行うだけでよいためです。
    
- [ビジネス サーバー 2015 の Skype のレコードを DNS の作成](create-dns-records.md): Skype でビジネスのサーバーが正常に動作するのには、いくつかの DNS 設定が場所にする必要があります。 これは、クライアントからサーバーにアクセスできるようにし、サーバーがお互いを認識できるようにするためです。 一度 DNS エントリを割り当てると、ドメイン全体で有効になるため、このような設定は展開ごとに 1 回行うだけでかまいません。
    
- [を作成するビジネス サーバー 2015 の Skype の新しいトポロジを公開し、](create-and-publish-new-topology.md) : ビジネスのサーバー システムに Skype をインストールするにはトポロジ内のサーバーごとに、前に、トポロジを作成し、発行する必要があります。 トポロジを公開するときは、トポロジの情報を中央管理ストア データベースに読み込みます。 Enterprise Edition プールの場合は、新しいトポロジを初めて公開するときに中央管理ストア データベースを作成することになります。 Standard Edition の場合は、トポロジを公開する前に、展開ウィザードから [最初の Standard Edition サーバーの準備] プロセスを実行する必要があります。 この操作を行うと、SQL Server Express Edition インスタンスのインストールと中央管理ストアの作成が行われ、Standard Edition が準備されます。
    
- [トポロジ内のサーバー上のビジネス サーバー 2015 の Skype のインストール](install-skype-for-business-server.md): トポロジが中央管理ストアにロードされ、Active Directory の役割を実行するサーバーが知っている、ビジネス サーバー システムに Skype をインストールする必要があります。各トポロジ内のサーバーです。
    
- [ビジネス サーバー 2015 の Skype のトポロジを確認](verify-the-topology.md)しますトポロジが正常に動作していることを確認する準備が整ったら、トポロジを公開し、各トポロジでは、サーバーにインストールされているサーバーのビジネス システムのコンポーネントの Skype があれば、。. 構成伝達されているすべての Active Directory サーバーにビジネス用の Skype が使用可能に、ドメイン内にドメイン全体が知っているように確認が含まれます。
    

