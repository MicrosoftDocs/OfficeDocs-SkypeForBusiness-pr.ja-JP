---
title: Skype for Business Server のアーカイブを展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '概要: このトピックでは、Skype for Business Server のアーカイブを展開する方法について説明します。'
ms.openlocfilehash: 32b25b373bd5399928d5e5eaed063c194942f697
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825217"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Skype for Business Server のアーカイブを展開する
 
**概要:** このトピックでは、Skype for Business Server のアーカイブを展開する方法について説明します。
  
アーカイブは Skype for Business Server 展開の各フロントエンド サーバーに自動的にインストールされますが、使用する前に初期セットアップと構成の手順を実行する必要があります。 始める前に [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)の概念を理解している必要があります。
  
## <a name="deployment-checklist"></a>展開チェックリスト

アーカイブの設定方法は、選択するストレージ オプションによって異なります。 
  
- 展開内のすべてのユーザーに Microsoft Exchange 統合を使用する場合は、ユーザーの Skype for Business Server アーカイブ ポリシーを構成する必要があります。 代わりに、Exchange In-Place 保持ポリシーを構成して、Exchange にホームのユーザーのメールボックスを保持In-Placeします。 これらのポリシーの構成の詳細については、Exchange 製品のドキュメントを参照してください。
    
- 展開内のすべてのユーザーに Microsoft Exchange 統合を使用しない場合は、Skype for Business Server アーカイブ データベース (SQL Server データベース) をトポロジに追加し、更新されたトポロジを公開してから、ユーザーのアーカイブ ポリシーと設定を構成する必要があります。 アーカイブ データベースは、初期トポロジの展開と同時に、または少なくとも 1 つのフロントエンド プールまたは Standard Edition サーバーを展開した後で展開できます。 このドキュメントでは、アーカイブ データベースを既存の展開に追加して展開する方法について説明します。
    
1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合は、展開内の他のすべてのフロントエンド プールと Standard Edition サーバーに対してアーカイブを有効にする必要があります。 これは、通信をアーカイブする必要があるユーザーは、別のプールでホストされるグループ IM 会話やミーティングに招待される可能性があるためです。 会話やミーティングがホストされているプールでアーカイブが有効になっていない場合は、完全なセッションをアーカイブすることはできません。 このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルおよび会議参加または退出イベントはアーカイブできません。
  
> [!IMPORTANT]
> コンプライアンス上の理由から組織でアーカイブが重要な場合は、アーカイブを展開し、ポリシーと他のオプションを適切なレベルで構成してから、該当するユーザー全員に対してアーカイブを有効にしてから、それらのユーザーを Skype for Business Server に対して有効にします。 
  
次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。
  
|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |Microsoft Exchange 統合 (一部またはすべてのユーザーのアーカイブ ストレージに Exchange を使用) を使用するには、既存の Exchange 展開が必要です。  <br/> 一部またはすべてのユーザーのアーカイブ ストレージに個別のアーカイブ データベース (SQL Server データベースを使用) を使用するには、アーカイブ データを格納するサーバー上SQL Serverを使用します。  <br/> アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバーで実行されます。 これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Skype for Business と Exchange の統合の計画](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Skype for Business Server 2019 のシステム要件](../../../SfBServer2019/plan/system-requirements.md) |
|**アーカイブをサポートする適切な内部トポロジを作成する (展開内のすべてのユーザーに Microsoft Exchange 統合を使用しない場合のみ)** <br/> |トポロジ ビルダーを実行して Skype for Business Server アーカイブ データベース (SQL Server データベース) をトポロジに追加し、トポロジを公開します。  <br/> |アーカイブ データベースを組み込むトポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウント。  <br/> トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Skype for Business Server ファイル ストアで使用するファイル共有に対するフル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できます)。  <br/> |[Skype for Business Server の既存の展開にアーカイブ データベースを追加する](add-archiving-databases.md) <br/> |
|**サーバー間認証を構成する (Microsoft Exchange 統合を使用する場合のみ)** <br/> |Skype for Business Server と Exchange の間の認証を有効にするためにサーバーを構成します。 **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** を実行して、アーカイブを有効にする前に Exchange アーカイブ ストレージ接続を検証することをお勧めします。 <br/> |サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。  <br/> |サーバー間認証を管理する  <br/> |
|**アーカイブ オプションとポリシーを構成する** <br/> |Microsoft Exchange 統合を使用するかどうか、グローバル ポリシーとサイト ポリシーとユーザー ポリシー (すべてのデータ ストレージに Microsoft Exchange 統合を使用しない場合)、および重要モード、データのエクスポートと削除などの特定のアーカイブ オプションを含む、アーカイブを構成します。  <br/> Microsoft Exchange 統合を使用する場合は、Exchange In-Place保持ポリシーを必要に応じて構成します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。あるいは、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。  <br/> |[Skype for Business Server のアーカイブ オプションを構成する](configure-archiving-options.md) <br/> Exchange 製品ドキュメント (Microsoft Exchange 統合を使用する場合)。  <br/> |
   

