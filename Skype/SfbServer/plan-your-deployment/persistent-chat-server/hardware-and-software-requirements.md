---
title: Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: このトピックでは、Skype for Business Server 2015 の常設チャットサーバーのハードウェア要件およびソフトウェア要件について説明します。'
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213233"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件
 
**概要:** このトピックでは、Skype for Business Server 2015 の常設チャットサーバーのハードウェアとソフトウェアの要件について説明します。
  
常設チャットサーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition と共にインストールできます。 要件は、インストールされている Skype for Business Server 2015 のエディションと、ビジネスのパフォーマンス要件によって異なります。 Enterprise Edition では、最大8万の同時ユーザーをサポートできます。Standard Edition は、最大2万の同時ユーザーをサポートできます。 常設チャットは、フロントエンドコンポーネントおよびバックエンド SQL データベースコンポーネントで構成されます。
  
常設チャットサーバーを展開する前に、次のハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。
  
- Skype for Business Server 2015、常設チャットサーバー、データベースサーバー、およびファイルサーバーをサポートするための最小要件を満たすハードウェア。 詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。
    
- サポートされているオペレーティングシステムとデータベースソフトウェア。
    
    サポートされているオペレーティングシステムとデータベースソフトウェア、および Windows 更新の要件の詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。
    
- Skype for Business Server 2015 フロントエンドサーバー。 フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャットサーバーと常設チャット機能を実行しているコンピューター間の通信を可能にします。 
    
- メッセージキューソフトウェア。 常設チャットサーバーおよび常設チャットコンプライアンスサービス (展開されている場合) によって使用されます。
    
次のセクションでは、常設チャットサーバーおよび常設チャットデータを格納するデータベースの特定の要件について説明します。

> [!NOTE] 
> 常設チャットは Skype for business Server 2015 で利用可能ですが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの概要](/microsoftteams/upgrade-start-here)」を参照してください。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかを選択できます。 
  
## <a name="front-end-server-requirements"></a>フロントエンドサーバーの要件

フロントエンドサーバーの要件は、常設チャットサーバーを Skype for Business Server 2015 Enterprise Edition または Standard Edition と共に展開するかどうかによって異なります。
  
- Skype for Business Server 2015 Enterprise Edition と共に常設チャットサーバーを展開している場合は、Enterprise Edition プール内の1つ以上のスタンドアロンコンピューターに常設チャットサーバーのフロントエンドサーバーを展開することができます。 常設チャットフロントエンドサーバーを Skype for Business Server 2015 フロントエンドサーバー上に併置することはできません。 
    
    1台の常設チャットサーバーフロントエンドサーバーでは、2万アクティブユーザーをサポートできます。 最大4つのアクティブなフロントエンドを持つ常設チャットサーバープールを使用して、合計8万の同時ユーザーをサポートすることができます。 
    
- Skype for Business Server 2015 Standard Edition で常設チャットサーバーを展開している場合は、常設チャットをフロントエンドサーバーと併置することができます。 この単一サーバーの展開では、最大2万ユーザーをサポートできます。 
    
## <a name="persistent-chat-server-database-requirements"></a>常設チャットサーバーのデータベースの要件

常設チャットサーバーには、チャットルームの履歴とコンテンツ、構成データ、ユーザープロビジョニングデータ、およびその他の関連メタデータを格納するための SQL Server データベースソフトウェアが必要です。 必要に応じて、常設チャットコンプライアンスデータベースを使用してコンプライアンスデータを保存します。 常設チャットデータベースは、バックエンドデータベースと同じ SQL Server、または同じ SQL インスタンスに併置できます。 
  
- Skype for Business Server 2015 Enterprise Edition と共に常設チャットサーバーをインストールする場合は、最適なパフォーマンスを確保するために、常設チャットのファイルストアをインストールすることをお勧めします。
    
- Skype for Business Server 2015 Standard edition で常設チャットサーバーをインストールする場合は、ローカルの SQL Server Express インスタンスに常設チャットストアバックエンドサーバーを展開することができます。
    
- 常設チャットデータベース (mgc) とコンプライアンスデータベース (メンバーサーバー) は、SQL Server の同じインスタンスまたは別の SQL Server に配置できます。
    
データベースサーバープラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認してから、前提条件となるソフトウェアをインストールします。 常設チャットデータベースサーバーのサーバープラットフォームには、Skype for Business Server 2015 バックエンドデータベースサーバーと同じハードウェアが必要です。 詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。
  
データベースサーバーで、次のいずれかのソフトウェアアプリケーションがインストールされていることを確認します。

- Microsoft SQL Server 2017 と最新のサービスパック。

- Microsoft SQL Server 2016 Service Pack 1。これは、Skype for Business Server の累積的な更新プログラム7以降のリリースで実行する必要があります。 SQL Server 2016 を最新のサービスパックと共に実行することをお勧めします。 Microsoft SQL Server 2016 をインストールする方法の詳細については、「 [INSTALL SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)」を参照してください。

- Microsoft SQL Server 2014 で、Skype for Business Server の累積的な更新プログラム6以降のリリースを使用して実行する必要があります。 SQL Server 2014 を最新のサービスパックと共に実行することをお勧めします。 Microsoft SQL Server 2014 をインストールする方法の詳細については、「 [INSTALL SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)」を参照してください。

- Microsoft SQL Server 2012 (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。 Microsoft SQL Server 2012 をインストールする方法の詳細については、「 [INSTALL SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)」を参照してください。

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャットサーバーの証明書の要件

証明書の取得、SQL Server データベースの作成、およびファイルストアの作成の詳細については、「 [Deploy Skype For Business Server 2015](../../deploy/deploy.md)」を参照してください。 
  
## <a name="for-more-information"></a>関連情報

ハードウェアとソフトウェアの要件の詳細については、以下のトピックを参照してください。
  
- [Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

