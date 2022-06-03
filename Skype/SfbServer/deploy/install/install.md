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
description: '概要: Skype for Business Serverのインストール用に環境を準備する方法について説明します。'
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860588"
---
# <a name="install-skype-for-business-server"></a>Skype for Business Server のインストール
 
**概要：** Skype for Business Serverのインストール用に環境を準備する方法について説明します。
  
この記事では、Skype for Business Serverのインストール例について説明します。 この記事では、完全なSkype for Business Serverインストールを実行するために必要なすべての手順については説明しません。 目標は、基本的な会議と共有の機能を含む、狭く定義されたトポロジでプロシージャの例を提供することです。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for Business Serverのインストール プロセスの概要

Skype for Business Serverのインストールには、さまざまな手順が含まれています。 環境で実行Skype for Business Server必要な手順は、環境の仕様によって異なります。 たとえば、WINDOWS Server for DNS を使用している場合は、DNS エントリを追加する手順の例を利用できます。 DNS に別のシステムを使用する場合は、特定の DNS システムの手順に従う必要があります。 これは、このセクションの多くの手順に当てはまります。
  
Skype for Business Serverは、Standard EditionとEnterprise Editionで使用できます。 主な違いは、Standard EditionがEnterprise Editionに含まれる高可用性機能をサポートしていない点です。 
  
Skype for Business Serverは高度な製品であり、正確なインストール プロセスは特定の状況に大きく依存します。 このセクションでは、製品をインストールするための一般的な手順について説明します。 ただし、環境や計画の決定によって、各手順が異なる場合があります。 たとえば、小規模な組織では 1 台のサーバーでSkype for Business Server Standard Editionを実行するのが適切な場合があります。一方、大規模な多国籍組織は、製品専用の世界中の場所に 50 台のサーバーを持つ場合があります。
  
> [!NOTE]
> 最新の累積的な更新プログラムの詳細については、「[Skype for Business Serverの更新プログラム」を](https://support.microsoft.com/kb/3061064)参照してください。 CU1 パッチをインストールした後、管理者はコマンドレットを  `Update-CsAdminRole` 実行する必要があります。 このコマンドレットは、リモート PowerShell 経由で新しい GCP コマンドレットにアクセスするために必要です。
  
> [!IMPORTANT]
> このセクションの手順は、狭く定義された一連の要件を使用した例として機能し、特定の決定が既に行われていると想定します。 Skype for Business Serverをインストールする必要がある実際の手順は、大きく異なる可能性があります。 このセクションの手順は例としてのみ使用し、すべての環境にSkype for Business Serverをインストールするためのステップ バイ ステップ ガイドとして使用しないでください。 
  
初めてSkype for Business Serverを起動して実行するには、8 つの主要な手順が必要です。 このセクションの手順例は、Skype for Business Serverのインストールに必要な手順だけではない点を理解しておく必要があります。 次の 8 つの手順は、プロセス全体をよりよく理解し、基本的な作業環境を稼働させるための例です。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示すように、手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 8 つの手順は次のとおりです。
  
![インストール プロセスの概要。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Skype for Business Serverの前提条件をインストール](install-prerequisites.md)する: Skype for Business Server トポロジを構成するすべてのサーバーに前提条件をインストールします。 前提条件は、すべてのロールで同じではありません。 たとえば、フロントエンド ロールを提供するサーバーには一連の前提条件があり、ディレクター ロールを提供するサーバーには異なる一連の前提条件があります。 詳細については、前提条件計画のドキュメントを参照してください。
    
- [Skype for Business Serverでファイル共有を作成](create-a-file-share.md)する: Skype for Business Server トポロジ全体でサーバーによって使用されるファイル共有を作成します。
    
- [Skype for Business Serverに管理ツールをインストール](install-administrative-tools.md)する: 管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。 トポロジ内の少なくとも 1 つのサーバー、またはSkype for Business ServerでサポートされているWindows OS バージョンを実行している 64 ビット管理ワークステーションに管理ツールをインストールする必要があります。
    
- [Skype for Business Server用に Active Directory を準備](prepare-active-directory.md)する: Skype for Business Server Active Directory と密接に連携します。 Skype for Business Serverを操作するには、Active Directory ドメインを準備する必要があります。 これを行うには、展開ウィザードを使用します。ドメインに対して 1 回だけ実行されます。 これは、プロセスによってグループが作成され、ドメインが変更され、1 回だけ行う必要があるためです。
    
- [Skype for Business Serverの DNS レコードを作成](create-dns-records.md)する: Skype for Business Serverが正常に動作するには、さまざまな DNS 設定を設定する必要があります。 これは、クライアントがサービスにアクセスする方法を知り、サーバーが互いについて知ることができるようにするためです。 DNS エントリを割り当てるとドメイン全体で使用できるため、これらの設定はデプロイごとに 1 回だけ完了する必要があります。
    
- [Skype for Business Serverで新しいトポロジを作成して発行](create-and-publish-new-topology.md)する: トポロジ内の各サーバーにSkype for Business Server システムをインストールする前に、トポロジを作成して公開する必要があります。 トポロジを発行すると、トポロジ情報が Central Management Microsoft Store データベースに読み込まれます。 これがEnterprise Edition プールの場合は、新しいトポロジを初めて発行するときに、Central Management Microsoft Store データベースを作成します。 これがStandard Editionの場合は、トポロジを発行する前に、展開ウィザードから最初のStandard Editionサーバーの準備プロセスを実行する必要があります。 これにより、SQL Server Express Edition インスタンスをインストールし、Central Management Microsoft Storeを作成することで、Standard Editionの準備が整います。
    
- [トポロジ内のサーバーにSkype for Business Serverをインストールする](install-skype-for-business-server.md): トポロジが Central Management Microsoft Storeに読み込まれ、Active Directory がどのサーバーがどの役割を実行するかを認識したら、トポロジ内の各サーバーにSkype for Business Server システムをインストールする必要があります。
    
- [Skype for Business Serverでトポロジを確認](verify-the-topology.md)する: トポロジが公開され、トポロジ内の各サーバーにインストールされているSkype for Business Server システム コンポーネントが完了したら、トポロジが期待どおりに動作していることを確認する準備が整います。 これには、構成がすべての Active Directory サーバーに伝達されたことを確認して、ドメイン全体でSkype for Businessが使用できることをドメイン全体で認識することが含まれます。
    

