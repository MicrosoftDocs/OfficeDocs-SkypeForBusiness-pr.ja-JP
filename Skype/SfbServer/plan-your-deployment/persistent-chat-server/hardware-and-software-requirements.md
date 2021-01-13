---
title: Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件
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
description: '概要: このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件について説明します。'
ms.openlocfilehash: 32ba0d94679e6f326fa1821cbe3401d031854037
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834537"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件
 
**概要:** このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件について説明します。
  
常設チャット サーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition と一緒にインストールできます。 要件は、インストールした Skype for Business Server 2015 のエディションと、ビジネスのパフォーマンス要件によって異なっています。 Enterprise Edition は最大 80,000 人の同時ユーザーをサポートできます。Standard Edition では、最大 20,000 人の同時ユーザーをサポートできます。 常設チャットは、フロントエンド コンポーネントと、データベース コンポーネントのSQL構成されます。
  
常設チャット サーバーを展開する前に、次のハードウェア要件とソフトウェア要件を満たしていることを確認する必要があります。
  
- Skype for Business Server 2015、常設チャット サーバー、データベース サーバー、およびファイル サーバーをサポートする最小要件を満たすハードウェア。 詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)のサーバー要件」を参照してください。
    
- サポートされているオペレーティング システムとデータベース ソフトウェア。
    
    サポートされているオペレーティング システムとデータベース ソフトウェア、および Windows 更新プログラムの要件の詳細については [、Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)のサーバー要件を参照してください。
    
- Skype for Business Server 2015 フロントエンド サーバー。 フロントエンド サーバーは、セッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャット サーバーを実行しているコンピューターと常設チャット機能間の通信を可能にします。 
    
- メッセージ キュー ソフトウェア。 常設チャット サーバーおよび常設チャット コンプライアンス サービスによって使用されます (展開されている場合)。
    
以下のセクションでは、常設チャット サーバーおよび常設チャット データを格納するデータベースの特定の要件について説明します。

> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
  
## <a name="front-end-server-requirements"></a>フロントエンド サーバーの要件

フロントエンド サーバーの要件は、Skype for Business Server 2015 Enterprise Edition と Standard Edition の組み合わされた常設チャット サーバーを展開するかどうかによって異なっています。
  
- Skype for Business Server 2015 Enterprise Edition を使用して常設チャット サーバーを展開する場合は、Enterprise Edition プール内の 1 つ以上のスタンドアロン コンピューターに常設チャット サーバー フロントエンド サーバーを展開できます。 常設チャット フロントエンド サーバーを Skype for Business Server 2015 フロント エンド サーバーに共に使用することはできません。 
    
    1 つの常設チャット サーバー フロントエンド サーバーで、20,000 人のアクティブ ユーザーをサポートできます。 最大 4 つのアクティブなフロントエンドを持つ常設チャット サーバー プールを使用して、合計 80,000 人の同時ユーザーをサポートできます。 
    
- Skype for Business Server 2015 Standard Edition と共に常設チャット サーバーを展開する場合は、常設チャットをフロント エンド サーバーと共に使用できます。 この単一サーバー展開では、最大 20,000 ユーザーをサポートできます。 
    
## <a name="persistent-chat-server-database-requirements"></a>常設チャット サーバー データベースの要件

常設チャット サーバーでは、SQL Server履歴とコンテンツ、構成データ、ユーザー プロビジョニング データ、その他の関連するメタデータを格納するために、データベース ソフトウェアを使用する必要があります。 必要に応じて、常設チャット コンプライアンス データベースを使用してコンプライアンス データを格納します。 常設チャット データベースは、バック エンド データベースと同じSQL Server、または同じ SQL インスタンスに同時に展開できます。 
  
- Skype for Business Server 2015 Enterprise Edition と一緒に常設チャット サーバーをインストールする場合は、最適なパフォーマンスを確保するために、常設チャット ファイル ストアをインストールしてください。
    
- Skype for Business Server 2015 Standard エディションを使用して常設チャット サーバーをインストールする場合は、ローカルの SQL Server Express インスタンスに常設チャット ストアのバック エンド サーバーを展開できます。
    
- 常設チャット データベース (mgc) とコンプライアンス データベース (mgccomp) は、SQL Server の同じインスタンス、または別の SQL サーバーに保存できます。
    
データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認してから、必要なソフトウェアをインストールします。 常設チャット データベース サーバーのサーバー プラットフォームには、Skype for Business Server 2015 のバック エンド データベース サーバーと同じハードウェアが必要です。 詳細については [、Skype for Business Server 2015 のサーバー要件を参照](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)してください。
  
データベース サーバーで、次のいずれかのソフトウェア アプリケーションがインストールされていることを確認します。

- Microsoft SQL Server 2017 と最新のサービス パック。

- Microsoft SQL Server 2016 Service Pack 1 を使用し、Skype for Business Server の累積的な更新プログラム 7 以降のリリースで実行する必要があります。 最新のサービス パックSQL Server 2016 年 1 月の実行をお勧めします。 Microsoft SQL Server 2016 のインストール方法の詳細については、「Install [SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)」を参照してください。

- Microsoft SQL Server 2014 では、Skype for Business Server の累積的な更新プログラム 6 以降のリリースで実行する必要があります。 最新のサービス パックSQL Server 2014 を実行してください。 Microsoft SQL Server 2014 のインストール方法の詳細については、「Install [SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)」を参照してください。

- Microsoft SQL Server 2012 (64 ビット版)、最新のサービス パックの実行をお勧めします。 Microsoft SQL Server 2012 のインストール方法の詳細については、「Install [SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)」を参照してください。

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャット サーバー証明書の要件

証明書の取得、SQL Server データベースの作成、およびファイル ストアの作成の詳細については [、「Skype for Business Server 2015](../../deploy/deploy.md)の展開」を参照してください。 
  
## <a name="for-more-information"></a>詳細情報

ハードウェアおよびソフトウェアの要件の詳細については、以下のトピックを参照してください。
  
- [Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

