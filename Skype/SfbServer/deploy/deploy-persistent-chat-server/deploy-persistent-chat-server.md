---
title: Skype for Business Server 2015 での常設チャット サーバーの展開
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '概要: は、Skype をビジネス 2015 永続的なチャット サーバーの展開方法について説明するには、このトピックを読みます。'
ms.openlocfilehash: b7b0e2731056eb1dd0584f0ba20d553d49ea2f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975999"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの展開
 
**の概要:** Skype ビジネス 2015 永続的なチャット サーバーを導入する方法の詳細については、このトピックを参照してください。
  
永続的なチャット サーバーを展開します。 
  
- トポロジ ビルダーを使用して定義、またはインポート、およびその後公開トポロジとコンポーネントを展開します。
    
- 永続的なチャット サーバーのコンポーネントを展開する環境を準備します。
    
- インストールおよび展開するための永続的なチャット サーバー コンポーネントを構成します。
    
永続的なチャット サーバーを展開する前に、「[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を読んでください。 計画のトピックでは、ハードウェアとソフトウェアの要件、使用できるトポロジ、併置のシナリオについて説明しています。 
  
> [!NOTE] 
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。 

## <a name="deployment-checklist"></a>展開チェックリスト

少なくとも 1 つの Skype ビジネス サーバーのフロント エンド プールまたは Standard Edition Server のビジネスの 1 つの Skype を含む、最初のトポロジを展開した後は、永続的なチャット サーバーを展開できます。 展開のチェックリストでは、永続的なチャット サーバーの展開に必要な基本的な手順について説明し、詳細についてはリンクを提供します。
  
**永続的なチャット サーバーの展開プロセス**

|**タスク**|**手順**|**必要な役割とグループ メンバーシップ**|**関連トピック**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> | システム要件を満たすハードウェアに、次をインストールします。 <br/>  固定サーバーのフロント エンド サーバーをチャットします。 <br/>  システム要件を満たすオペレーティング システム <br/>  Skype をビジネスのサーバーを実行しているコンピューターのソフトウェアの前提条件 <br/>  永続的なチャット サーバーのデータベースをホストするサーバー。 <br/>  サポートされるバージョンの SQL Server <br/>  永続的なチャット サーバーのコンプライアンスが必要な場合。 <br/>  永続的なチャット サーバーのコンプライアンス データベースをホストするサーバー上の SQL Server <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**永続的なチャット サーバー (および必要に応じて、永続的なチャットのコンプライアンス) をサポートするために適切な内部トポロジを作成します。** <br/> | 永続的なチャット サーバー プールをトポロジに追加するのにはトポロジ ビルダーを実行します。 <br/>  コンポーネントの永続的なチャット サーバーをトポロジに追加します。 <br/>  永続的なチャット サーバー ストア (および災害復旧のためのバックアップ SQL Server) の SQL Server データベースを作成します。 <br/>  ビジネス ファイル ストア新しい Skype の定義や、ビジネスのファイル ストアの永続的なチャット サーバーのファイルを既存の Skype を使用 <br/>  この永続的なチャット サーバー プールに要求をルーティングすることができますビジネス サーバー プールの Skype を関連付ける <br/>  常設チャット コンプライアンスが必要な場合 <br/>  チャット コンプライアンスの永続ストアを追加します。 <br/>  コンプライアンスを有効にする永続的なチャット サーバー プールの定義] チェック ボックスをクリックします。 <br/>  トポロジを公開します。 <br/>  Standard Edition では、永続的なチャット サーバーをインストールする場合は、永続的なチャット サーバー プールの完全修飾ドメイン名 (FQDN) が Standard Edition サーバーと一致する必要があり、SQL Server データベースは SQL Server Express のインスタンスで、標準は、1 か所に配置エディションのサーバー <br/> |トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。  <br/> トポロジを公開するには、Domain Admins グループと RTCUniversalServerAdmins グループ、およびユーザーのメンバーであるアカウントもフル コントロールのアクセス許可 (読み取り/書き込み/変更) に必要ファイル ストアのビジネス用の Skype (は永続的なチャット サーバーのファイルのそのトポロジ ビルダーが Dacl を構成、必要な)。  <br/> |[Skype for Business Server 2015 での新しいトポロジの作成および公開](../../deploy/install/create-and-publish-new-topology.md) <br/> [ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。](add-persistent-chat-server.md) <br/> |
|**常設チャット サーバーの展開** <br/> | 永続的なチャット サーバーを実行しているすべてのコンピューターで、Skype のビジネス サーバーのセットアップを実行します。 永続的なチャット サーバーのセットアップは次の手順を提供するビジネス サーバーの展開ウィザードの Skype に統合されます。 <br/>  ローカル管理ストアを展開する。 <br/>  永続的なチャット サービスをインストールします。 <br/>  証明書を要求および割り当てる。 <br/>  サービスを実行および開始する。 <br/> |ローカルの Administrators グループのメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 での常設チャット サーバーの展開](deploy-persistent-chat-server.md) <br/> |
|**常設チャット管理者を作成する** <br/> |ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。  <br/> |ドメイン管理者のメンバーであるユーザー。  <br/> |[Skype for Business Server 2015 での常設チャット管理者の作成](create-a-persistent-chat-administrator.md) <br/> |
|**常設チャット サーバーの構成** <br/> | 次のようにユーザーを構成します。 <br/>  ユーザーは、永続的なチャット サーバーへのアクセス ポリシーで有効にするのには。 既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。 <br/>  設定の構成 <br/> |ユーザーは CsPersistentChatAdministrator のメンバーであることが必要です。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator であることが必要です。  <br/> |[Skype for Business Server 2015 での常設チャット サーバーの管理](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

