---
title: Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: Skype for Business Server 2015 の常設チャットサーバーのハードウェアとソフトウェアの要件については、こちらのトピックを参照してください。'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418446"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件
 
**概要:** このトピックを読むと、Skype for Business Server 2015 の常設チャットサーバーのハードウェアとソフトウェアの要件について知ることができます。
  
常設チャットサーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition と共にインストールできます。 要件は、インストールされている Skype for Business Server 2015 のエディションと、ビジネスのパフォーマンス要件によって異なります。 Enterprise Edition は、最大8万ユーザーを同時にサポートできます。Standard Edition は、最大2万人の同時ユーザをサポートしています。 常設チャットは、フロントエンドコンポーネントとバックエンド SQL データベースコンポーネントで構成されます。
  
常設チャットサーバーを展開する前に、次のハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。
  
- Skype for Business Server 2015、常設チャットサーバー、データベースサーバー、およびファイルサーバーをサポートするための最小要件を満たしているハードウェア。 詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。
    
- サポートされているオペレーティング システムおよびデータベース ソフトウェア。
    
    サポートされているオペレーティングシステムとデータベースソフトウェア、および Windows の更新の要件の詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。
    
- Skype for Business Server 2015 フロントエンドサーバー。 フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤です。これにより、常設チャットサーバーを実行しているコンピューターと常設チャット機能を実行しているコンピューター間の通信が可能になります。 
    
- メッセージ キュー ソフトウェア。 常設チャットサーバーと常設チャットコンプライアンスサービス (展開されている場合)。
    
以下のセクションでは、常設チャットサーバーと永続的なチャットデータを格納するデータベースの固有の要件について説明します。

> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 
  
## <a name="front-end-server-requirements"></a>フロント エンド サーバーの要件

フロントエンドサーバーの要件は、常設チャットサーバーを Skype for Business Server 2015 Enterprise Edition と Standard Edition のどちらで展開するかによって異なります。
  
- Skype for Business Server 2015 Enterprise Edition で常設チャットサーバーを展開する場合は、Enterprise Edition プールの1つ以上のスタンドアロンコンピューターに常設チャットサーバーフロントエンドサーバーを展開できます。 Skype for Business Server 2015 フロントエンドサーバーでは、常設チャットフロントエンドサーバーを検索することはできません。 
    
    1つの常設チャットサーバーフロントエンドサーバーは、2万アクティブユーザーをサポートできます。 最大4つのアクティブなフロントエンドの常設チャットサーバープールを使用して、合計8万人の同時ユーザーをサポートすることができます。 
    
- Skype for Business Server 2015 Standard Edition で常設チャットサーバーを展開している場合は、フロントエンドサーバーで常設チャットを検索することができます。 この単一サーバーの展開では、最大2万ユーザーをサポートできます。 
    
## <a name="persistent-chat-server-database-requirements"></a>常設チャットサーバーのデータベース要件

常設チャットサーバーには、チャットルームの履歴とコンテンツ、構成データ、ユーザープロビジョニングデータ、およびその他の関連するメタデータを保存するための SQL Server データベースソフトウェアが必要です。 必要に応じて、常設チャットのコンプライアンスデータベースを使ってコンプライアンスデータを保存します。 常設チャットデータベースは、同一の SQL Server、または同じ SQL インスタンスに、バックエンドデータベースとして併置できます。 
  
- Skype for Business Server 2015 Enterprise Edition との常設チャットサーバーをインストールする場合は、最適なパフォーマンスを確保するために、常設チャットファイルストアをインストールすることをお勧めします。
    
- Skype for Business Server 2015 Standard edition で常設チャットサーバーをインストールする場合は、ローカルの SQL Server Express インスタンスに常設チャットストアバックエンドサーバーを展開することができます。
    
- 常設チャットデータベース (行う) とコンプライアンスデータベース () は、SQL Server の同じインスタンスまたは別の SQL server に配置できます。
    
データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認した後、必要なソフトウェアをインストールします。 常設チャットデータベースサーバーのサーバープラットフォームには、Skype for Business Server 2015 バックエンドデータベースサーバーと同じハードウェアが必要です。 詳細については、「[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。
  
次のどちらかのソフトウェア アプリケーションがデータベース サーバーにインストールされていることを確認してください。

- 最新の service pack を搭載した Microsoft SQL Server 2017

- Microsoft SQL Server 2016 Service Pack 1 と共に、Skype for Business Server 累積更新プログラム7以降で実行する必要があります。 最新の service pack で SQL Server 2016 を実行することをお勧めします。 Microsoft SQL Server 2016 のインストール方法の詳細については、「 [Sql server 2016 をインストール](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)する」を参照してください。

- Microsoft SQL Server 2014 で、Skype for Business Server 累積更新プログラム6以降で実行する必要があります。 最新の service pack で SQL Server 2014 を実行することをお勧めします。 Microsoft SQL Server 2014 のインストール方法の詳細については、「 [Sql server 2014 をインストール](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)する」を参照してください。

- Microsoft SQL Server 2012 (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。 Microsoft SQL Server 2012 のインストール方法の詳細については、「 [Sql server 2012 をインストール](https://go.microsoft.com/fwlink/p/?LinkID=248559)する」を参照してください。

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャットサーバー証明書の要件

証明書の取得、SQL Server データベースの作成、ファイルストアの作成について詳しくは、「 [Skype For Business Server 2015 の展開](../../deploy/deploy.md)」をご覧ください。 
  
## <a name="for-more-information"></a>関連情報

ハードウェアおよびソフトウェアの要件の詳細については、次のトピックを参照してください。
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

