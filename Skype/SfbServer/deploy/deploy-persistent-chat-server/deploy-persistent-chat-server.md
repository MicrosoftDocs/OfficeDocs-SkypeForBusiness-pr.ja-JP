---
title: Skype for Business Server 2015 での常設チャット サーバーの展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '概要: このトピックでは、Skype for Business Server 2015 常設チャット サーバーを展開する方法について説明します。'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830477"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの展開
 
**概要:** このトピックでは、Skype for Business Server 2015 常設チャット サーバーを展開する方法について説明します。
  
常設チャット サーバーを展開するには、次の方法を実行します。 
  
- トポロジ ビルダーを使用して、展開するトポロジとコンポーネントを定義またはインポートし、その後公開する
    
- 常設チャット サーバー コンポーネントを展開する環境を準備する
    
- 展開用に常設チャット サーバー コンポーネントをインストールおよび構成する
    
常設チャット サーバーを展開する前に [、「Plan for Persistent Chat Server in Skype for Business Server 2015」](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。 計画のトピックでは、ハードウェアとソフトウェアの要件、考えられるトポロジ、および一覧のシナリオについて説明します。 
  
> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 

## <a name="deployment-checklist"></a>展開チェックリスト

少なくとも 1 つの Skype for Business Server フロント エンド プールまたは 1 つの Skype for Business Standard Edition サーバーを含む初期トポロジを展開した後に、常設チャット サーバーを展開できます。 展開チェックリストでは、常設チャット サーバーの展開に必要な基本的な手順について説明し、詳細なリンクを示します。
  
**常設チャット サーバーの展開プロセス**

|**タスク**|**手順**|**必要な役割およびグループ メンバーシップ**|**関連トピック**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> | システム要件を満たすハードウェアに、次のものをインストールします。 <br/>  常設チャット サーバーのフロント エンド サーバー: <br/>  システム要件を満たすオペレーティング システム <br/>  Skype for Business Server を実行しているコンピューターのソフトウェア前提条件 <br/>  常設チャット サーバー データベースをホストするサーバーで、次の条件を実行します。 <br/>  サポートされているバージョンのSQL Server <br/>  常設チャット サーバーのコンプライアンスが必要な場合: <br/>  SQL Server 常設チャット サーバー コンプライアンス データベースをホストするサーバー上のサーバー上にインストールされます。 <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**常設チャット サーバー (およびオプションで常設チャットコンプライアンス) をサポートする適切な内部トポロジを作成する** <br/> | トポロジ ビルダーを実行して、常設チャット サーバー プールをトポロジに追加します。 <br/>  常設チャット サーバー コンポーネントをトポロジに追加する <br/>  常設チャット SQL Server (および障害復旧用のバックアップ データベース) SQL Serverデータベースを作成します。 <br/>  新しい Skype for Business ファイル ストアを定義するか、既存の Skype for Business ファイル ストアを常設チャット サーバー ファイルに使用する <br/>  この常設チャット サーバー プールに要求をルーティングできる Skype for Business Server プールを関連付ける <br/>  常設チャットのコンプライアンスが必要な場合: <br/>  常設チャット コンプライアンス ストアの追加 <br/>  コンプライアンスを有効にする常設チャット サーバー プール定義のチェック ボックスをオンにする <br/>  トポロジを公開します。 <br/>  常設チャット サーバーを Standard Edition にインストールする場合、常設チャット サーバー プールの完全修飾ドメイン名 (FQDN) が Standard Edition サーバーと一致し、SQL Server データベースが Standard Edition サーバー上の SQL Server Express インスタンスに一致している必要があります。 <br/> |トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。  <br/> トポロジを公開するには、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであり、ユーザーは、Skype for Business File Store for Persistent Chat Server ファイルに対するフル コントロールのアクセス許可 (読み取り/書き込み/変更) も必要です (トポロジ ビルダーが必要な DACL を構成できる)。  <br/> |[Skype for Business Server 2015 での新しいトポロジの作成と公開](../../deploy/install/create-and-publish-new-topology.md) <br/> [Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加](add-persistent-chat-server.md) <br/> |
|**常設チャット サーバーの展開** <br/> | 常設チャット サーバーを実行しているすべてのコンピューターで Skype for Business Server のセットアップを実行します。 常設チャット サーバーのセットアップは、Skype for Business Server 展開ウィザードに統合され、次の手順が提供されます。 <br/>  ローカル管理ストアを展開する。 <br/>  常設チャット サービスのインストール <br/>  証明書を要求および割り当てる。 <br/>  サービスを実行および開始する。 <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 での常設チャット サーバーの展開](deploy-persistent-chat-server.md) <br/> |
|**常設チャット管理者の作成** <br/> |ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。  <br/> |ドメイン管理者のメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 での常設チャット管理者の作成](create-a-persistent-chat-administrator.md) <br/> |
|**常設チャット サーバーの構成** <br/> | 次のようにユーザーを構成します。 <br/>  常設チャット サーバーにアクセスするには、ポリシーでユーザーを有効にする必要があります。 既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。 <br/>  設定の構成 <br/> |ユーザーは CsPersistentChatAdministrator のメンバーである必要がある。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator である必要がある。  <br/> |[Skype for Business Server 2015 での常設チャット サーバーの管理](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

