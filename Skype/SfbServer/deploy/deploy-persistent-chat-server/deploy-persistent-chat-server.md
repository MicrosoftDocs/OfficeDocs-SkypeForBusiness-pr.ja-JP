---
title: Skype for Business Server 2015 での常設チャット サーバーの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '概要: Skype for Business Server 2015 常設チャットサーバーを展開する方法については、このトピックを参照してください。'
ms.openlocfilehash: fed07d864bda6fc3e0e93932123b2651c226b4f6
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418116"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの展開
 
**概要:** このトピックでは、Skype for Business Server 2015 常設チャットサーバーを展開する方法について説明します。
  
常設チャットサーバーを展開するには、次の操作を行います。 
  
- トポロジビルダーを使用して、トポロジと展開するコンポーネントを定義またはインポートし、後で公開します。
    
- 常設チャットサーバーコンポーネントを展開するための環境の準備
    
- 展開用の常設チャットサーバーコンポーネントのインストールと構成
    
常設チャットサーバーを展開する前に、「 [Skype For Business server 2015 の常設チャットサーバーの計画」](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。 計画のトピックでは、ハードウェアとソフトウェアの要件、使用できるトポロジ、併置のシナリオについて説明しています。 
  
> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 

## <a name="deployment-checklist"></a>展開チェックリスト

少なくとも1つの Skype for Business Server フロントエンドプールまたは1つの Skype for Business Standard Edition Server を含む、最初のトポロジを展開した後で、常設チャットサーバーを展開することができます。 展開チェックリストは、常設チャットサーバーを展開するために必要な基本的な手順について説明し、詳細情報のリンクを提供します。
  
**常設チャットサーバーの展開プロセス**

|**Task**|**手順**|**必要な役割とグループ メンバーシップ**|**関連トピック**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> | システム要件を満たすハードウェアに、次をインストールします。 <br/>  常設チャットサーバーのフロントエンドサーバーで、次の操作を行います。 <br/>  システム要件を満たすオペレーティング システム <br/>  Skype for Business Server を実行しているコンピューターのソフトウェア要件 <br/>  常設チャットサーバーデータベースをホストするサーバー上で、次の操作を行います。 <br/>  サポートされるバージョンの SQL Server <br/>  常設チャットサーバーのコンプライアンスが必要な場合: <br/>  常設チャットサーバーのコンプライアンスデータベースをホストするサーバー上の SQL Server <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**常設チャットサーバーをサポートするための適切な内部トポロジを作成します (また、必要に応じて常設チャットのコンプライアンスも可能)。** <br/> | トポロジビルダーを実行して、常設チャットサーバープールをトポロジに追加します。 <br/>  常設チャットサーバーコンポーネントをトポロジに追加する <br/>  常設チャットサーバーストア用の SQL Server データベースを作成します (および障害回復用のバックアップ SQL Server)。 <br/>  新しい Skype for Business ファイルストアを定義するか、既存の Skype for Business ファイルストアで常設チャットサーバーファイルを使用する <br/>  要求をこの常設チャットサーバープールにルーティングできる Skype for Business Server プールを関連付ける <br/>  常設チャット コンプライアンスが必要な場合 <br/>  常設チャットのコンプライアンスストアを追加する <br/>  コンプライアンスを有効にするには、[常設チャットサーバープールの定義] チェックボックスをオンにします。 <br/>  トポロジを公開します。 <br/>  標準エディションに常設チャットサーバーをインストールする場合は、常設チャットサーバープールの完全修飾ドメイン名 (FQDN) が standard Edition サーバーと一致する必要があります。 SQL Server データベースは、標準の SQL Server Express インスタンスに併置されています。エディションサーバー <br/> |トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。  <br/> トポロジ (Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであるアカウント) を公開するには、常設チャットサーバーファイル用の Skype for Business ファイルストアでもフルコントロールのアクセス許可 (読み取り/書き込み/変更) が必要です (そのため、このトポロジビルダーは、必要な Dacl を構成できます。  <br/> |[Skype for Business Server 2015 での新しいトポロジの作成および公開](../../deploy/install/create-and-publish-new-topology.md) <br/> [Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する](add-persistent-chat-server.md) <br/> |
|**常設チャット サーバーの展開** <br/> | 常設チャットサーバーを実行しているすべてのコンピューターで、Skype for Business Server のセットアップを実行します。 常設チャットサーバーのセットアップは、次の手順に従って、Skype for Business Server 展開ウィザードに統合されています。 <br/>  ローカル管理ストアを展開する。 <br/>  常設チャットサービスをインストールする <br/>  証明書を要求および割り当てる。 <br/>  サービスを実行および開始する。 <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 での常設チャット サーバーの展開](deploy-persistent-chat-server.md) <br/> |
|**常設チャット管理者の作成** <br/> |ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。  <br/> |ドメイン管理者のメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 での常設チャット管理者の作成](create-a-persistent-chat-administrator.md) <br/> |
|**常設チャット サーバーの構成** <br/> | 次のようにユーザーを構成します。 <br/>  ユーザは、常設チャットサーバにアクセスするためにポリシーによって有効になっている必要があります。 既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。 <br/>  設定の構成 <br/> |ユーザーは CsPersistentChatAdministrator のメンバーであることが必要です。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator であることが必要です。  <br/> |[Skype for Business Server 2015 での常設チャット サーバーの管理](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

