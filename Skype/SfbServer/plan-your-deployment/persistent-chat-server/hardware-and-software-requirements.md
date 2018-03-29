---
title: Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件の詳細については、このトピックを読みます。'
ms.openlocfilehash: a56f939360edae0da47198e4a3810f70712b6ab8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件
 
**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件の詳細については、このトピックを参照してください。
  
ビジネス サーバー 2015 の Enterprise Edition または Standard Edition は、Skype で永続的なチャット サーバーをインストールできます。 要件は、ビジネス サーバー 2015 の Skype のエディションをインストールして、ビジネスのパフォーマンスの要件によって異なります。 Enterprise Edition は 80,000 同時ユーザーまでサポートできます。Standard Edition は、最大 20,000 人のユーザーをサポートできます。 永続的なチャットは、フロント エンド コンポーネントとバック エンド SQL のデータベース コンポーネントで構成されます。
  
永続的なチャット サーバーを展開する前に、次のハードウェアおよびソフトウェアの要件が満たされていることを確認する必要があります。
  
- ビジネス サーバー 2015、永続的なチャット サーバー、データベース サーバー、およびファイル ・ サーバの Skype をサポートするために最低限の要件を満たしているハードウェアです。 詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。
    
- サポートされているオペレーティング システムおよびデータベース ソフトウェア。
    
    詳細についてはサポートされているオペレーティング システムおよびデータベース ソフトウェア、および Windows の更新の必要性、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。
    
- ビジネス 2015 のフロント エンド サーバーの Skype です。 フロント エンド サーバーは、のセッション開始プロトコル (SIP) ルーティングでは、永続的なチャット サーバーとの永続的なチャット機能を実行しているコンピューター間の通信を実現する基盤です。 
    
- メッセージ キュー ソフトウェア。 展開されている場合は、永続的なチャット サーバーと永続的なチャット コンプライアンス サービスで使用されます。
    
次のセクションでは、永続的なチャット サーバーと永続的なチャット データを格納しているデータベースの特定の要件について説明します。
  
## <a name="front-end-server-requirements"></a>フロント エンド サーバーの要件

フロント エンド サーバーの要件は、Skype でチャットのサーバーが永続的なビジネス サーバー 2015 の Enterprise Edition または Standard Edition を展開するかどうかによって異なります。
  
- ビジネス サーバー 2015 エンタープライズ エディションの Skype での永続的なチャット サーバーを展開する場合、永続的なチャット サーバー フロント エンド サーバー Enterprise Edition プール内の 1 つまたは複数のスタンドアロン コンピューターに展開できます。 永続的なチャット フロント エンド サーバー上、Skype を連結できない場合は、ビジネス 2015 フロント エンド サーバーにします。 
    
    1 つ永続的なチャット サーバー フロント エンド サーバーでは、20,000 のアクティブなユーザーをサポートできます。 80,000 の同時接続ユーザーの合計をサポートできるため、最大 4 つのアクティブなフロント エンドを持つ永続的なチャット サーバー プールを持つことができます。 
    
- ビジネス サーバー 2015 の Standard Edition の Skype での永続的なチャット サーバーを展開する場合は、フロント エンド サーバーとの永続的なチャットを集約できます。 このシングル サーバー配置では、最大 20,000 ユーザーをサポートできます。 
    
## <a name="persistent-chat-server-database-requirements"></a>永続的なチャット サーバーのデータベースの要件

永続的なチャット サーバーには、チャットの履歴とコンテンツ、構成データ、ユーザー プロビジョニング データ、およびその他の関連するメタデータを格納する SQL Server データベースのソフトウェアが必要です。 必要に応じて、コンプライアンス データを格納するのに永続的なチャット コンプライアンス データベースを使用します。 同一の SQL Server、または、同じ SQL インスタンスも、バックエンド データベースとの永続的なチャット データベースを共存させることができます。 
  
- ビジネス サーバー 2015 エンタープライズ エディションの Skype で永続的なチャット サーバーをインストールする場合、最適なパフォーマンスを確実にお勧め、永続的なチャットのファイル ストアをインストールすることです。
    
- ビジネス サーバー 2015 Standard edition は、Skype で永続的なチャット サーバーをインストールする場合、永続的なチャット ストア バック エンド サーバーのローカルの SQL Server Express インスタンスに配置できます。
    
- (Mgc) 永続的なチャット データベースとコンプライアンス データベース (mgccomp) は、別の SQL サーバーまたは SQL Server の同じインスタンスに配置できます。
    
データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認した後、必要なソフトウェアをインストールします。 データベースの永続的なチャット サーバーのサーバー プラットフォームでは、ビジネス サーバー 2015 のバックエンド データベース サーバーに、Skype と同じハードウェアが必要です。 詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。
  
次のどちらかのソフトウェア アプリケーションがデータベース サーバーにインストールされていることを確認してください。
  
- Microsoft SQL Server 2012。 Microsoft SQL Server 2012 をインストールする方法の詳細については、 [SQL Server 2012 のインストール](https://go.microsoft.com/fwlink/p/?LinkID=248559)を参照してください。
    
- Microsoft SQL Server 2008 R2。 Microsoft SQL Server の 2008 R2 をインストールする方法の詳細については、 [SQL Server のインストール (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702)を参照してください。
    
## <a name="persistent-chat-server-certificate-requirements"></a>永続的なチャット サーバーの証明書の要件

詳細証明書の取得については、SQL Server データベースを作成して、ファイル ストアを作成する[ビジネス サーバー 2015 の Skype の導入](../../deploy/deploy.md)を参照してください。 
  
## <a name="for-more-information"></a>関連情報

ハードウェアおよびソフトウェアの要件の詳細については、次のトピックを参照してください。
  
- [ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [ビジネス サーバー 2015 の Skype の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

