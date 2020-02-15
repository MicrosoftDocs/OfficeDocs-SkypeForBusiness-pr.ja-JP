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
description: '概要: Skype for Business Server のインストールのために環境を準備する方法について説明します。 次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。'
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042384"
---
# <a name="install-skype-for-business-server"></a>Skype for Business Server のインストール
 
**概要:** Skype for Business Server のインストールのために環境を準備する方法について説明します。 次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。
  
この記事では、Skype for Business Server のインストール例について説明します。 この記事では、Skype for Business Server の完全インストールを実行するために必要なすべての手順については説明しません。 ここでの目的は、基本的な会議と共有機能を備えた、限定された定義のトポロジで手順例を提供することです。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for Business Server のインストールプロセスの概要

Skype for Business Server のインストールには、さまざまな手順が含まれています。 環境内で実行されている Skype for Business Server を入手するために必要な手順は、環境の仕様によって異なります。 たとえば、DNS に Windows Server を使用している場合は、DNS エントリを追加するための例の手順を利用することができます。 DNS に別のシステムを使用する場合は、特定の DNS システムについて手順に従う必要があります。 これは、このセクションの手順の多くに当てはまります。
  
Skype for Business Server は、Standard Edition と Enterprise Edition で利用できます。 主な違いは、Standard Edition は Enterprise Edition に含まれる高可用性機能をサポートしていないことです。 
  
Skype for Business Server は advanced product で、正確なインストールプロセスは特定の状況に大きく依存します。 このセクションでは、製品をインストールするための一般的な手順について順を追って説明します。 ただし、各手順は環境や計画の決定に応じて異なる場合があります。 たとえば、小規模な組織の場合、Skype for Business Server Standard Edition を実行しているサーバーが1台の場合は適切な場合がありますが、大規模な多国籍組織では、製品専用の地域に50サーバーが存在する場合があります。
  
> [!NOTE]
> 最新の累積的な更新プログラムの詳細については、「 [Skype For Business Server の更新プログラム](https://support.microsoft.com/kb/3061064)」を参照してください。 CU1 パッチをインストールした後、管理者が`Update-CsAdminRole`コマンドレットを実行する必要があります。 このコマンドレットは、リモート PowerShell 経由で新しい GCP コマンドレットにアクセスするために必要です。
  
> [!IMPORTANT]
> このセクションの手順は、限定された定義済みの要件セットを使用して、特定の決定が既に行われていることを前提としています。 Skype for Business Server をインストールするために必要な手順は、大きく異なる可能性があります。 このセクションの手順は、すべての環境に Skype for Business Server をインストールするためのステップバイステップガイドとしてではなく、一例として使用してください。 
  
Skype for Business Server を初めて実行するときには、8つの主要な手順が必要になります。 このセクションの手順の例は、Skype for Business Server のインストールに必要な手順だけではないことを理解しておく必要があります。 次の8つの手順は、プロセス全体の理解を深め、基本的な作業環境を稼働させるための簡単な例です。 手順1から5までを任意の順序で実行できます。 ただし、手順6、7、および8は、図に示されているように、手順 1 ~ 5 の後で実行する必要があります。 8つの手順は次のとおりです。
  
![インストールプロセスの概要。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- Skype for business [server の前提条件のインストール](install-prerequisites.md): Skype For business server トポロジを構成するすべてのサーバーに必須コンポーネントをインストールします。 前提条件は、すべての役割に対して同じではありません。 たとえば、フロントエンドの役割を提供するサーバーには一連の前提条件があり、ディレクターの役割を提供するサーバーには、異なる一連の前提条件があります。 詳細については、前提条件の計画に関するドキュメントを参照してください。
    
- [Skype For Business server でファイル共有を作成](create-a-file-share.md)する: skype For business server トポロジ全体でサーバーが使用するファイル共有を作成します。
    
- [Skype For Business Server での管理ツールのインストール](install-administrative-tools.md): 管理ツールには、トポロジビルダーとコントロールパネルがあります。 管理ツールは、トポロジ内の少なくとも1つのサーバー、または Skype for Business Server でサポートされている Windows OS バージョンを実行している64ビットの管理ワークステーションにインストールする必要があります。
    
- [Skype for Business server 用の Active directory を準備する](prepare-active-directory.md): Skype For business Server は active directory と緊密に連携します。 Skype for Business Server と連携するには、Active Directory ドメインを準備する必要があります。 この操作は展開ウィザードを使用して行うことができ、ドメインに対して1回だけ実行されます。 これは、プロセスによってグループが作成され、ドメインが変更されるため、1回だけ実行する必要があるためです。
    
- [Skype for Business server の DNS レコードの作成](create-dns-records.md): Skype For business server が正しく動作するためには、いくつかの dns 設定を行う必要があります。 これは、クライアントがサービスにアクセスする方法と、サーバーが相互に認識していることを認識できるようにするためです。 これらの設定は、展開ごとに1回だけ実行する必要があります。一度 DNS エントリを割り当てると、ドメイン全体で使用できるようになります。
    
- [Skype For Business server で新しいトポロジを作成および公開](create-and-publish-new-topology.md)する: トポロジ内の各サーバーに Skype For business server システムをインストールするには、まずトポロジを作成して発行する必要があります。 トポロジを公開すると、サーバーの全体管理ストアデータベースにトポロジ情報が読み込まれます。 これが Enterprise Edition プールの場合は、新しいトポロジを最初に公開するときに中央管理ストアデータベースを作成します。 Standard Edition の場合は、トポロジを公開する前に、展開ウィザードから [最初の Standard Edition サーバーの準備] プロセスを実行する必要があります。 これにより、SQL Server Express Edition のインスタンスをインストールして中央管理ストアを作成することで、Standard Edition の準備ができます。
    
- [トポロジ内のサーバーへの skype For Business server のインストール](install-skype-for-business-server.md): トポロジを中央管理ストアに読み込み、Active Directory でどのサーバーがどの役割を実行するかがわかっている場合は、トポロジ内の各サーバーに Skype For business server システムをインストールする必要があります。
    
- [Skype For Business server のトポロジを確認](verify-the-topology.md)する: トポロジが公開されており、トポロジ内の各サーバーに Skype For business server システムコンポーネントがインストールされている場合は、トポロジが想定どおりに機能していることを確認できます。 これには、ドメイン全体で Skype for Business がドメインで利用可能であることがわかるように、すべての Active Directory サーバーに構成が反映されていることを確認することが含まれます。
    

