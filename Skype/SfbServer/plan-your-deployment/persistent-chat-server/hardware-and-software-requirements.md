---
title: 2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server
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
ms.localizationpriority: medium
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: このトピックを参照して、2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Serverしてください。'
ms.openlocfilehash: a8ee506d9bee1e99727dab2da18f70f3c6278664
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630431"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server
 
**概要:** このトピックでは、2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Serverしてください。
  
常設チャット サーバーは、2015 年 2015 年Skype for Business ServerまたはEnterprise EditionインストールStandard Edition。 要件は、インストールした 2015 Skype for Business Serverのエディションと、ビジネスのパフォーマンス要件によって異なっています。 Enterprise Edition最大 80,000 人の同時ユーザーをサポートできます。Standard Edition最大 20,000 人の同時ユーザーをサポートできます。 常設チャットは、フロントエンド コンポーネントと、データベース コンポーネントのSQL構成されます。
  
常設チャット サーバーを展開する前に、次のハードウェア要件とソフトウェア要件が満たされている必要があります。
  
- 2015、常設チャット サーバー Skype for Business Serverデータベース サーバー、およびファイル サーバーをサポートする最小要件を満たすハードウェア。 詳細については[、「Server requirements for Skype for Business Server 2015」を参照してください](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- サポートされているオペレーティング システムとデータベース ソフトウェア。
    
    サポートされているオペレーティング システムとデータベース ソフトウェア、および更新Windowsの詳細については[、「Server requirements for Skype for Business Server 2015」](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。
    
- Skype for Business Server 2015 フロントエンド サーバー。 フロントエンド サーバーはセッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャット サーバーを実行しているコンピューターと常設チャット機能間の通信を可能にします。 
    
- メッセージ キュー ソフトウェア。 常設チャット サーバーと常設チャット コンプライアンス サービスで使用されます (展開されている場合)。
    
次のセクションでは、常設チャット サーバーの特定の要件と、常設チャット データを格納するデータベースについて説明します。

> [!NOTE] 
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 
  
## <a name="front-end-server-requirements"></a>フロントエンド サーバーの要件

フロントエンド サーバーの要件は、2015 年 2015 年に常設チャット サーバーを展開するSkype for Business ServerまたはEnterprise EditionによってStandard Edition。
  
- Skype for Business Server 2015 Enterprise Edition を使用して常設チャット サーバーを展開する場合は、Enterprise Edition プール内の 1 つ以上のスタンドアロン コンピューターに常設チャット サーバー フロント エンド サーバーを展開できます。 2015 年 2015 年のフロント エンド サーバー上の常設チャット フロント エンド サーバーをSkype for Business Serverすることはできません。 
    
    1 つの常設チャット サーバー フロント エンド サーバーは、20,000 人のアクティブ ユーザーをサポートできます。 最大 4 つのアクティブなフロントエンドを持つ常設チャット サーバー プールを使用して、合計 80,000 人の同時ユーザーをサポートできます。 
    
- 常設チャット サーバーを Skype for Business Server 2015 Standard Editionで展開する場合は、常設チャットをフロント エンド サーバーと照合できます。 この単一サーバー展開では、最大 20,000 人のユーザーをサポートできます。 
    
## <a name="persistent-chat-server-database-requirements"></a>常設チャット サーバー データベースの要件

常設チャット サーバーでは、SQL Server履歴とコンテンツ、構成データ、ユーザー プロビジョニング データ、その他の関連するメタデータを格納するために、データベース ソフトウェアを使用する必要があります。 必要に応じて、常設チャット コンプライアンス データベースを使用してコンプライアンス データを格納します。 常設チャット データベースは、バック エンド データベースと同じSQL Server、または同じSQLインスタンスに対して同じ場所に展開できます。 
  
- Skype for Business Server 2015 Enterprise Edition を使用して常設チャット サーバーをインストールする場合は、最適なパフォーマンスを確保するために、常設チャット ファイル ストアをインストールしてください。
    
- Skype for Business Server 2015 Standard Edition を使用して常設チャット サーバーをインストールする場合は、常設チャット ストア のバック エンド サーバーをローカル SQL Server Express インスタンスに展開できます。
    
- 常設チャット データベース (mgc) とコンプライアンス データベース (mgccomp) は、SQL Server の同じインスタンスまたは別の SQL サーバーにSQLできます。
    
データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認し、前提条件ソフトウェアをインストールします。 常設チャット データベース サーバーのサーバー プラットフォームには、2015 年のSkype for Business Serverサーバーと同じハードウェアが必要です。 詳細については[、「Server requirements for Skype for Business Server 2015」を参照してください](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
データベース サーバーで、次のいずれかのソフトウェア アプリケーションがインストールされていることを確認します。

- Microsoft SQL Serverサービス パックを使用して 2017 年にリリースされました。

- Microsoft SQL Server 2016 を Service Pack 1 で使用し、累積的な更新プログラム 7 以降Skype for Business Serverを使用して実行する必要があります。 最新のサービス パックSQL Server 2016 年の実行をお勧めします。 2016 のインストール方法の詳細Microsoft SQL Server [2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)のインストールSQL Server参照してください。

- Microsoft SQL Server 2014 では、累積的な更新プログラム 6 以降Skype for Business Serverを使用して実行する必要があります。 最新のサービス SQL Server 2014 の実行をお勧めします。 2014 のインストール方法のMicrosoft SQL Serverについては[、「Install SQL Server 2014」を参照](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)してください。

- Microsoft SQL Server 2012 (64 ビット 版)、最新のサービス パックで実行をお勧めします。 2012 のインストール方法のMicrosoft SQL Serverについては[、「Install SQL Server 2012」を参照してください](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110))。

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャット サーバー証明書の要件

証明書の取得、SQL Server データベースの作成、およびファイル ストアの作成の詳細については[、「Deploy Skype for Business Server 2015」を参照](../../deploy/deploy.md)してください。 
  
## <a name="for-more-information"></a>詳細情報

ハードウェア要件とソフトウェア要件の詳細については、次のトピックを参照してください。
  
- [2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [2015 年の環境Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
