---
title: 常設チャット サーバーを 2015 年Skype for Business Server展開する
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
description: '概要: このトピックを参照して、2015 常設チャット Skype for Business Server展開する方法について説明します。'
ms.openlocfilehash: bfe287184426fd1dc856d8dc29bf1f13cb0720bffcdf392791bb75b9813b383e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314893"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>常設チャット サーバーを 2015 年Skype for Business Server展開する
 
**概要:** このトピックでは、2015 常設チャット Skype for Business Server展開する方法について説明します。
  
常設チャット サーバーを展開するには、次の条件を実行します。 
  
- トポロジ ビルダーを使用して、トポロジと展開するコンポーネントを定義またはインポートし、その後公開します。
    
- 常設チャット サーバー コンポーネントを展開する環境を準備する
    
- 展開用の常設チャット サーバー コンポーネントをインストールして構成する
    
常設チャット サーバーを展開する前に[、「2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)年の常設チャット サーバーの計画」をSkype for Business Serverしてください。 計画のトピックでは、ハードウェアとソフトウェアの要件、可能なトポロジ、およびコロケーションシナリオについて説明します。 
  
> [!NOTE] 
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 

## <a name="deployment-checklist"></a>展開チェックリスト

少なくとも 1 つのフロントエンド プールまたは 1 つのサーバーを含む、初期トポロジを展開した後Skype for Business Server常設チャット サーバー Skype for Business Standard Editionできます。 展開チェックリストでは、常設チャット サーバーを展開するために必要な基本的な手順について説明し、詳細についてはリンクを提供します。
  
**常設チャット サーバーの展開プロセス**

|**タスク**|**手順**|**必要な役割およびグループ メンバーシップ**|**関連トピック**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> | システム要件を満たすハードウェアに、次のものをインストールします。 <br/>  常設チャット サーバーのフロント エンド サーバーでは、次の情報を使用します。 <br/>  システム要件を満たすオペレーティング システム <br/>  アプリケーションを実行しているコンピューターのソフトウェアSkype for Business Server <br/>  常設チャット サーバー データベースをホストするサーバーで、次の条件を実行します。 <br/>  サポートされているバージョンのSQL Server <br/>  常設チャット サーバーのコンプライアンスが必要な場合は、次の条件を満たします。 <br/>  SQL Server常設チャット サーバー コンプライアンス データベースをホストするサーバー上のサーバー上のサーバーの構成 <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015 年の環境Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**常設チャット サーバーをサポートする適切な内部トポロジを作成します (必要に応じて、常設チャットのコンプライアンス)** <br/> | トポロジ ビルダーを実行して、常設チャット サーバー プールをトポロジに追加します。 <br/>  常設チャット サーバー コンポーネントをトポロジに追加する <br/>  常設チャット SQL Serverストア用のデータベースを作成する (および障害復旧SQL Serverバックアップ) <br/>  新しいファイル ストアSkype for Business定義するか、常設チャット サーバー ファイルSkype for Business既存のファイル ストアを使用する <br/>  この常設チャット Skype for Business Serverに要求をルーティングできるプールを関連付ける <br/>  常設チャットのコンプライアンスが必要な場合: <br/>  常設チャット コンプライアンス ストアの追加 <br/>  コンプライアンスを有効にする場合は、[常設チャット サーバー プール定義] チェック ボックスをクリックします。 <br/>  トポロジを公開します。 <br/>  Standard Edition に常設チャット サーバーをインストールする場合、常設チャット サーバー プールの完全修飾ドメイン名 (FQDN) が Standard Edition サーバーと一致し、SQL Server データベースが Standard Edition サーバー上の SQL Server Express インスタンスに同一の場所にある必要があります。 <br/> |トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。  <br/> トポロジを発行するには、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであるアカウントで、ユーザーが常設チャット サーバー ファイルの Skype for Business ファイル ストアでフル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つ必要があります (トポロジ ビルダーが必要な DACL を構成できます)。  <br/> |[2015 年に新しいトポロジをSkype for Business Serverする](../../deploy/install/create-and-publish-new-topology.md) <br/> [常設チャット サーバーを 2015 Skype for Business Serverトポロジに追加する](add-persistent-chat-server.md) <br/> |
|**常設チャット サーバーの展開** <br/> | 常設チャット Skype for Business Server実行しているすべてのコンピューターで、サーバーのセットアップを実行します。 常設チャット サーバーのセットアップは、次の手順をSkype for Business Server展開ウィザードに統合されています。 <br/>  ローカル管理ストアを展開する。 <br/>  常設チャット サービスのインストール <br/>  証明書を要求および割り当てる。 <br/>  サービスを実行および開始する。 <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[常設チャット サーバーを 2015 年Skype for Business Server展開する](deploy-persistent-chat-server.md) <br/> |
|**常設チャット管理者の作成** <br/> |ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。  <br/> |ドメイン管理者のメンバーであるユーザー。  <br/> |[2015 年に常設チャット管理者をSkype for Business Serverする](create-a-persistent-chat-administrator.md) <br/> |
|**常設チャット サーバーの構成** <br/> | 次のようにユーザーを構成します。 <br/>  常設チャット サーバーにアクセスするには、ポリシーでユーザーを有効にする必要があります。 既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。 <br/>  設定の構成 <br/> |ユーザーは CsPersistentChatAdministrator のメンバーである必要がある。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator である必要がある。  <br/> |[2015 年の常設チャット サーバー Skype for Business Serverする](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

