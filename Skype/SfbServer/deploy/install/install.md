---
title: Skype for Business Server のインストール
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
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '概要: Skype for Business Server のインストールのために環境を準備する方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: cac618aba9f97237e585ffc57b99c71a8a5c8645
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797088"
---
# <a name="install-skype-for-business-server"></a>Skype for Business Server のインストール
 
**概要:** Skype for Business Server のインストールのために環境を準備する方法について説明します。 Skype for Business Server の無料トライアルは、次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターからダウンロードしてください。
  
この記事では、Skype for Business Server のインストール例について説明します。 この記事では、Skype for Business Server の完全インストールを実行するために必要な手順について説明します。 基本的な会議および共有機能を含む、狭義のトポロジの手順例を提供することを目的としています。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for Business Server のインストールプロセスの概要

Skype for Business Server のインストールには、さまざまな手順が含まれています。 環境で実行されている Skype for Business Server を入手するために必要な手順は、環境の仕様によって異なります。 たとえば、DNS として Windows Server を使用する場合は、DNS エントリを追加する手順例が役に立ちます。 DNS として別のシステムを使用する場合は、特定の DNS システムの手順に従う必要があります。 これは、このセクションの多くの手順に当てはまります。
  
Skype for Business Server は、Standard Edition と Enterprise Edition で利用できます。 2 つのエディションの主な違いは、Enterprise Edition には含まれている高可用性機能を Standard Edition ではサポートしていない点です。 
  
Skype for Business Server は高度な製品であり、正確なインストール手順は、特定の状況に応じて大きく異なります。 このセクションでは、この製品をインストールするための一般的な手順について順を追って説明します。 ただし、各手順は環境や計画事項によって異なる場合があります。 たとえば、小規模の組織では、Skype for Business Server Standard Edition を実行するのが適切な単一サーバーの場合、大規模な多国籍組織では、その製品専用の地域で50サーバーを利用できます。
  
> [!NOTE]
> 最新の累積的な更新については、「 [Skype For Business Server の更新プログラム](https://support.microsoft.com/en-us/kb/3061064)」を参照してください。 CU1 の修正プログラムをインストールした後、管理`Update-CsAdminRole`者がコマンドレットを実行する必要があります。 このコマンドレットは、リモート PowerShell 経由で新しい GCP コマンドレットにアクセスするために必要です。
  
> [!IMPORTANT]
> このセクションの手順は、狭義に定義された一連の要件を使用する例を示すことを目的としており、何らかの具体的な決定が既に行われているものと仮定しています。 Skype for Business Server をインストールするために必要な実際の手順は、大きく異なる可能性があります。 このセクションの手順は例として使用してください。すべての環境に Skype for Business Server をインストールするためのステップバイステップガイドとしては使用しません。 
  
Skype for Business Server を初めて起動して実行するには、8つの主な手順が必要です。 このセクションの例の手順は、Skype for Business Server をインストールするために必要な手順だけではないことを理解しておく必要があります。 次の 8 つの手順は、全体的なプロセスの理解を深め、基本的な作業環境を立ち上げるための一例にすぎません。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。 8 つの手順は次のとおりです。
  
![インストール プロセスの概要](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Skype For business server の前提条件をインストール](install-prerequisites.md)する: Skype For business server トポロジを構成するすべてのサーバーに前提条件をインストールします。 前提条件はどの役割でも同じというわけではない点に注意してください。 たとえば、フロントエンドの役割を提供するサーバーとディレクターの役割を提供するサーバーとでは、前提条件となる機能のセットが異なります。 詳細については、前提条件の計画ドキュメントを参照してください。
    
- [Skype For Business server でファイル共有を作成](create-a-file-share.md)する: skype For business server トポロジ全体でサーバーが使用するファイル共有を作成します。
    
- [Skype For Business Server で管理ツールをインストール](install-administrative-tools.md)する: 管理ツールには、トポロジビルダーとコントロールパネルが含まれます。 Skype for Business Server でサポートされている Windows OS のバージョンを実行している場合は、トポロジまたは64ビットの管理ワークステーションの少なくとも1つのサーバーに管理ツールをインストールする必要があります。
    
- [Skype for Business server 用 Active directory の準備](prepare-active-directory.md): Skype For business Server は active directory と密接に連携します。 Skype for Business Server を使用するには、Active Directory ドメインを準備する必要があります。 このプロセスは展開ウィザードによって実行され、ドメインに対して 1 回のみ行います。 これは、プロセスによってグループの作成とドメインの変更が実行されるため、1 回行うだけでよいためです。
    
- [Skype For Business server の dns レコードを作成](create-dns-records.md)する: skype For business server が正常に動作するためには、いくつかの dns 設定が必要です。 これは、クライアントからサーバーにアクセスできるようにし、サーバーがお互いを認識できるようにするためです。 一度 DNS エントリを割り当てると、ドメイン全体で有効になるため、このような設定は展開ごとに 1 回行うだけでかまいません。
    
- [Skype For Business server で新しいトポロジを作成して公開](create-and-publish-new-topology.md)する: トポロジ内の各サーバーに skype For business server システムをインストールするには、トポロジを作成して公開する必要があります。 トポロジを公開するときは、トポロジの情報を中央管理ストア データベースに読み込みます。 Enterprise Edition プールの場合は、新しいトポロジを初めて公開するときに中央管理ストア データベースを作成することになります。 Standard Edition の場合は、トポロジを公開する前に、展開ウィザードから [最初の Standard Edition サーバーの準備] プロセスを実行する必要があります。 この操作を行うと、SQL Server Express Edition インスタンスのインストールと中央管理ストアの作成が行われ、Standard Edition が準備されます。
    
- [トポロジ内のサーバーに Skype For Business server をインストール](install-skype-for-business-server.md)する: トポロジが中央管理ストアに読み込まれ、Active Directory でどのサーバーがどの役割を実行するかがわかっている場合は、トポロジの各サーバーに Skype For business Server システムをインストールする必要があります。
    
- [Skype For Business server でトポロジを確認](verify-the-topology.md)する: トポロジを公開した後、トポロジ内の各サーバーに Skype For business server システムコンポーネントをインストールしたら、トポロジが予期したとおりに機能していることを確認できます。 これには、構成がすべての Active Directory サーバーに伝達されていることを確認することが含まれます。これにより、ドメイン全体で Skype for Business がドメインで利用可能であると認識されるようになります。
    

