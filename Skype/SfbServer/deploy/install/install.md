---
title: Skype for Business Server のインストール
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
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '概要: Skype for Business Server のインストール用に環境を準備する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: ef562a56e1129481954f9345a46483156bd1202f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801917"
---
# <a name="install-skype-for-business-server"></a>Skype for Business Server のインストール
 
**概要:** Skype for Business Server のインストール用に環境を準備する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
この記事では、Skype for Business Server のインストール例について説明します。 この記事では、Skype for Business Server の完全なインストールを実行するために必要なすべての手順については説明しません。 目標は、基本的な meet-and share 機能を含む、狭く定義されたトポロジの手順例を提供します。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for Business Server のインストール プロセスの概要

Skype for Business Server のインストールには、さまざまな手順が含まれています。 環境内で Skype for Business Server を実行するために必要な手順は、環境の詳細によって異なります。 たとえば、DNS に Windows Server を使用している場合は、DNS エントリを追加する手順の例を利用できます。 DNS に別のシステムを使用する場合は、特定の DNS システムの手順に従う必要があります。 これは、このセクションの多くの手順に当てはっています。
  
Skype for Business Server は Standard Edition と Enterprise Edition で利用できます。 主な違いは、Standard Edition が Enterprise Edition に含まれる高可用性機能をサポートしていない点です。 
  
Skype for Business Server は高度な製品であり、正確なインストール プロセスは特定の状況に大きな依存します。 このセクションでは、製品をインストールする一般的な手順について説明します。 ただし、各手順は、環境や計画の決定に応じて異なる場合があります。 たとえば、小規模な組織では単一サーバーで Skype for Business Server Standard Edition を実行する方が適切ですが、大規模な多国籍組織では、製品専用の世界中の場所に 50 台のサーバーを持つ場合があります。
  
> [!NOTE]
> 最新の累積的な更新プログラムの詳細については [、Skype for Business Server の更新プログラムを参照してください](https://support.microsoft.com/kb/3061064)。 CU1 パッチをインストールした後、管理者はコマンドレットを実行する必要  `Update-CsAdminRole` があります。 このコマンドレットは、リモート PowerShell を使用して新しい GCP コマンドレットにアクセスするために必要です。
  
> [!IMPORTANT]
> このセクションの手順は、狭く定義された一連の要件を使用する例として機能し、特定の決定が既に行われたと想定します。 Skype for Business Server をインストールするために必要な実際の手順は、多くの場合、大きな違いがあります。 このセクションの手順は、すべての環境に Skype for Business Server をインストールする手順ガイドとしてではなく、例としてのみ使用してください。 
  
Skype for Business Server を初めて稼働するには、8 つの主要な手順が必要です。 このセクションの手順例は、Skype for Business Server のインストールに必要な手順だけではないと理解している必要があります。 次の 8 つの手順は、プロセス全体をよりよく理解し、基本的な作業環境を稼働状態にするのに役立つ例です。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。 8 つの手順は次のとおりです。
  
![インストール プロセスの概要。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Skype for Business Server の前提条件のインストール](install-prerequisites.md) : Skype for Business Server トポロジを構成しているすべてのサーバーに前提条件をインストールします。 前提条件は、すべての役割で同じではありません。 たとえば、フロントエンドの役割を提供するサーバーは前提条件のセットを持ち、ディレクターの役割を提供するサーバーには異なる前提条件のセットがあります。 詳細については、前提条件となる計画に関するドキュメントを参照してください。
    
- [Skype for Business Server](create-a-file-share.md) でファイル共有を作成する : Skype for Business Server トポロジ全体でサーバーによって使用されるファイル共有を作成します。
    
- [Skype for Business Server に管理ツールを](install-administrative-tools.md) インストールする : 管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。 管理ツールは、トポロジ内の少なくとも 1 台のサーバー、または Skype for Business Server でサポートされている Windows OS バージョンを実行している 64 ビットの管理ワークステーションにインストールする必要があります。
    
- [Skype for Business Server 用の Active Directory の](prepare-active-directory.md) 準備 : Skype for Business Server は Active Directory と密接に関連して動作します。 Skype for Business Server で動作するには、Active Directory ドメインを準備する必要があります。 展開ウィザードを使用してこれを行うだけで、ドメインに対して 1 回だけ実行できます。 これは、プロセスによってグループが作成され、ドメインが変更され、1 回だけ行う必要があるためです。
    
- [Skype for Business Server](create-dns-records.md) の DNS レコードを作成する : Skype for Business Server が正しく動作するには、多数の DNS 設定を設定する必要があります。 これにより、クライアントはサービスへのアクセス方法を知り、サーバーは互いを知っています。 これらの設定は展開ごとに 1 回だけ完了する必要があります。DNS エントリを割り当てると、ドメイン全体で使用できます。
    
- [Skype for Business Server](create-and-publish-new-topology.md) で新しいトポロジを作成して公開する : トポロジ内の各サーバーに Skype for Business Server システムをインストールする前に、トポロジを作成して公開する必要があります。 トポロジを公開するときに、トポロジ情報を中央管理ストア データベースに読み込む必要があります。 Enterprise Edition プールの場合は、新しいトポロジを初めて公開する際に中央管理ストア データベースを作成します。 これが Standard Edition の場合は、トポロジを公開する前に展開ウィザードから最初の Standard Edition サーバーの準備プロセスを実行する必要があります。 これにより、Standard Edition の準備として、SQL Server Express Edition インスタンスをインストールし、中央管理ストアを作成します。
    
- トポロジ内のサーバーに[Skype for Business Server](install-skype-for-business-server.md)をインストールする : トポロジが中央管理ストアに読み込まれ、Active Directory でどのサーバーがどの役割を実行するのかを確認したら、トポロジ内の各サーバーに Skype for Business Server システムをインストールする必要があります。
    
- [Skype for Business Server](verify-the-topology.md) のトポロジを確認します。トポロジを公開し、トポロジ内の各サーバーに Skype for Business Server システム コンポーネントをインストールしたら、トポロジが期待通り動作している状態を確認できます。 これには、構成がすべての Active Directory サーバーに伝達され、ドメイン全体が Skype for Business がドメイン内で利用可能なことを知っていることを確認する機能が含まれます。
    

