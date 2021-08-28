---
title: ユーザーのアーカイブを展開Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '概要: このトピックを参照して、ユーザーのアーカイブを展開する方法Skype for Business Server。'
ms.openlocfilehash: 405946cb863c72399115b869f33bf8d107cec455
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606576"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>ユーザーのアーカイブを展開Skype for Business Server
 
**概要:** このトピックでは、ユーザーのアーカイブを展開する方法についてSkype for Business Server。
  
アーカイブは、Skype for Business Server 展開の各フロントエンド サーバーに自動的にインストールされますが、使用するには、初期セットアップと構成手順を実行する必要があります。 開始する前に、「プラン for archiving in Skype for Business Server」 の[概念に精通Skype for Business Server。](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="deployment-checklist"></a>展開チェックリスト

アーカイブの設定方法は、選択するストレージ オプションによって異なります。 
  
- 展開内のすべてのユーザー Exchange Microsoft Exchange統合を使用する場合は、ユーザーのアーカイブ ポリシー Skype for Business Server構成する必要があります。 代わりに、Exchange In-Place 保持ポリシーを構成して、Exchange に設定されているユーザーのアーカイブをサポートし、メールボックスを In-Place 保持します。 これらのポリシーの構成の詳細については、「Exchange」を参照してください。
    
- 展開内のすべてのユーザーに Microsoft Exchange 統合を使用しない場合は、Skype for Business Server アーカイブ データベース (SQL Server データベース) をトポロジに追加し、更新されたトポロジを発行してから、ユーザーのアーカイブ ポリシーと設定を構成する必要があります。 アーカイブ データベースは、初期トポロジの展開と同時に展開するか、少なくとも 1 つのフロントエンド プールまたはサーバーを展開した後Standard Editionできます。 このドキュメントでは、アーカイブ データベースを既存の展開に追加して展開する方法について説明します。
    
1 つのフロント エンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合は、展開内の他のすべてのフロントエンド プールと Standard Edition サーバーでアーカイブを有効にする必要があります。 これは、通信をアーカイブする必要があるユーザーは、別のプールでホストされるグループ IM 会話やミーティングに招待される可能性があるためです。 会話やミーティングがホストされているプールでアーカイブが有効になっていない場合は、完全なセッションをアーカイブすることはできません。 このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルおよび会議参加または退出イベントはアーカイブできません。
  
> [!IMPORTANT]
> コンプライアンス上の理由から組織でアーカイブが重要な場合は、アーカイブを展開し、ポリシーなどのオプションを適切なレベルで構成してから、適切なすべてのユーザーに対してアーカイブを有効にしてから、それらのユーザーを Skype for Business Server で有効にします。 
  
次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。
  
|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |Microsoft Exchange統合 (Exchangeまたはすべてのユーザーのアーカイブ ストレージに使用する) を使用するには、既存のExchange必要があります。  <br/> 一部またはすべてのユーザーのアーカイブ ストレージに個別のアーカイブ データベース (SQL Server データベースを使用する) を使用するには、アーカイブ データを格納するサーバー SQL Serverを使用します。  <br/> アーカイブは、プールとサーバーのフロントエンド サーバー Enterprise実行Standard Editionされます。 これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015 年の環境Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Skype for Business と Exchange の統合の計画](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[2019 年のSkype for Business Server要件](../../../SfBServer2019/plan/system-requirements.md) |
|**アーカイブをサポートする適切な内部トポロジを作成します (展開内のすべてのユーザーに Microsoft Exchange統合を使用しない場合のみ)** <br/> |トポロジ ビルダーを実行して、Skype for Business Serverデータベース (SQL Server) をトポロジに追加し、トポロジを公開します。  <br/> |アーカイブ データベースを組み込むトポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウントを指定します。  <br/> トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Skype for Business Server ファイル ストアに使用するファイル共有に対する完全な制御アクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できます)。  <br/> |[アーカイブ データベースを既存の展開に追加Skype for Business Server](add-archiving-databases.md) <br/> |
|**サーバー間認証を構成する (Microsoft サーバー統合を使用する場合Exchangeのみ)** <br/> |サーバーを構成して、サーバー間の認証Skype for Business ServerとExchange。 アーカイブを有効にする **前に、Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** を実行して、Exchange アーカイブ ストレージ接続を検証することをお勧めします。 <br/> |サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。  <br/> |サーバー間認証の管理  <br/> |
|**アーカイブ オプションとポリシーを構成する** <br/> |Microsoft Exchange 統合、グローバル ポリシー、サイトとユーザー ポリシー (すべてのデータ ストレージに Microsoft Exchange 統合を使用しない場合)、クリティカル モードやデータのエクスポートおよび削除などの特定のアーカイブ オプションを含むアーカイブを構成します。  <br/> Microsoft Exchange統合を使用する場合は、必要にExchange In-Place保持ポリシーを構成します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。あるいは、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。  <br/> |[サーバーのアーカイブ オプションを構成Skype for Business Server](configure-archiving-options.md) <br/> Exchangeドキュメント (Microsoft の統合を使用している場合Exchange)。  <br/> |
   

