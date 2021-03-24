---
title: Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件については、このトピックを参照してください。'
ms.openlocfilehash: d4609d557e5c55b680c4c0761f24cc4f320afcbd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095111"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件
 
**概要:** Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件について説明します。
  
常設チャット サーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition と一緒にインストールできます。 要件は、インストールした Skype for Business Server 2015 のエディションと、ビジネスのパフォーマンス要件によって異なっています。 Enterprise Edition では、最大 80,000 人の同時ユーザーをサポートできます。Standard Edition では、最大 20,000 人の同時ユーザーをサポートできます。 常設チャットは、フロントエンド コンポーネントと、データベース コンポーネントのSQL構成されます。
  
常設チャット サーバーを展開する前に、次のハードウェア要件とソフトウェア要件が満たされている必要があります。
  
- Skype for Business Server 2015、常設チャット サーバー、データベース サーバー、およびファイル サーバーをサポートする最小要件を満たすハードウェア。 詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)のサーバー要件」を参照してください。
    
- サポートされているオペレーティング システムとデータベース ソフトウェア。
    
    サポートされているオペレーティング システムとデータベース ソフトウェア、および Windows 更新プログラムの要件の詳細については [、「Server requirements for Skype for Business Server 2015」を参照](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)してください。
    
- Skype for Business Server 2015 フロントエンド サーバー。 フロントエンド サーバーはセッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャット サーバーを実行しているコンピューターと常設チャット機能間の通信を可能にします。 
    
- メッセージ キュー ソフトウェア。 常設チャット サーバーと常設チャット コンプライアンス サービスで使用されます (展開されている場合)。
    
次のセクションでは、常設チャット サーバーの特定の要件と、常設チャット データを格納するデータベースについて説明します。

> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
  
## <a name="front-end-server-requirements"></a>フロントエンド サーバーの要件

フロントエンド サーバーの要件は、Skype for Business Server 2015 Enterprise Edition または Standard Edition を使用して常設チャット サーバーを展開するかどうかによって異なっています。
  
- Skype for Business Server 2015 Enterprise Edition を使用して常設チャット サーバーを展開する場合は、Enterprise Edition プール内の 1 つ以上のスタンドアロン コンピューターに常設チャット サーバー フロント エンド サーバーを展開できます。 Skype for Business Server 2015 フロントエンド サーバー上の常設チャット フロント エンド サーバーを照合することはできません。 
    
    1 つの常設チャット サーバー フロント エンド サーバーは、20,000 人のアクティブ ユーザーをサポートできます。 最大 4 つのアクティブなフロントエンドを持つ常設チャット サーバー プールを使用して、合計 80,000 人の同時ユーザーをサポートできます。 
    
- Skype for Business Server 2015 Standard Edition を使用して常設チャット サーバーを展開する場合は、常設チャットをフロントエンド サーバーと照合できます。 この単一サーバー展開では、最大 20,000 人のユーザーをサポートできます。 
    
## <a name="persistent-chat-server-database-requirements"></a>常設チャット サーバー データベースの要件

常設チャット サーバーでは、SQL Server履歴とコンテンツ、構成データ、ユーザー プロビジョニング データ、その他の関連するメタデータを格納するために、データベース ソフトウェアを使用する必要があります。 必要に応じて、常設チャット コンプライアンス データベースを使用してコンプライアンス データを格納します。 常設チャット データベースは、バック エンド データベースと同じSQL Server、または同じSQLインスタンスに対して共有できます。 
  
- 最適なパフォーマンスを確保するために、Skype for Business Server 2015 Enterprise Edition を使用して常設チャット サーバーをインストールする場合は、常設チャット ファイル ストアをインストールしてください。
    
- Skype for Business Server 2015 Standard Edition を使用して常設チャット サーバーをインストールする場合は、常設チャット ストア のバック エンド サーバーをローカル の SQL Server Express インスタンスに展開できます。
    
- 常設チャット データベース (mgc) とコンプライアンス データベース (mgccomp) は、SQL Server サーバーの同じインスタンスまたは異なる SQL サーバーにSQLできます。
    
データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認し、前提条件ソフトウェアをインストールします。 常設チャット データベース サーバーのサーバー プラットフォームには、Skype for Business Server 2015 のバック エンド データベース サーバーと同じハードウェアが必要です。 詳細については [、「Skype for Business Server 2015 のサーバー](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)要件」を参照してください。
  
データベース サーバーで、次のいずれかのソフトウェア アプリケーションがインストールされていることを確認します。

- Microsoft SQL Serverサービス パックを使用して 2017 年にリリースされました。

- Microsoft SQL Server 2016 Service Pack 1 を使用し、Skype for Business Server 累積的な更新プログラム 7 以降のリリースで実行する必要があります。 最新のサービス SQL Server 2016 の実行をお勧めします。 2016 のインストール方法のMicrosoft SQL Serverについては [、「Install SQL Server 2016」を参照](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)してください。

- Microsoft SQL Server 2014 で、Skype for Business Server 累積的な更新プログラム 6 以降のリリースで実行する必要があります。 最新のサービス パックSQL Server 2014 年の実行をお勧めします。 2014 のインストール方法のMicrosoft SQL Serverについては [、「Install SQL Server 2014」を参照](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)してください。

- Microsoft SQL Server 2012 (64 ビット 版)、最新のサービス パックで実行をお勧めします。 2012 年にインストールする方法のMicrosoft SQL Server、「Install [SQL Server 2012」を参照してください](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110))。

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャット サーバー証明書の要件

証明書の取得、SQL Server データベースの作成、ファイル ストアの作成の詳細については [、「Deploy Skype for Business Server 2015」を参照](../../deploy/deploy.md)してください。 
  
## <a name="for-more-information"></a>詳細情報

ハードウェア要件とソフトウェア要件の詳細については、次のトピックを参照してください。
  
- [Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
