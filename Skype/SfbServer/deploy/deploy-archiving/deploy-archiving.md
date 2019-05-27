---
title: Skype for Business Server のアーカイブの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '概要: Skype for Business Server のアーカイブを展開する方法については、このトピックを参照してください。'
ms.openlocfilehash: 813911dba5bfc662ee1c6bea9dab99e34c031e98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286531"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Skype for Business Server のアーカイブの展開
 
**概要:** Skype for Business Server のアーカイブを展開する方法については、こちらのトピックを参照してください。
  
アーカイブは、Skype for Business Server の展開の各フロントエンドサーバーに自動的にインストールされますが、使用するには、最初のセットアップと構成の手順を実行する必要があります。 作業を始める前に、「 [Skype For Business Server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」の概念に精通していることを確認してください。
  
## <a name="deployment-checklist"></a>展開チェックリスト

アーカイブのセットアップ方法は、選択するストレージ オプションによって異なります。 
  
- 展開のすべてのユーザーに対して Microsoft Exchange 統合を使用している場合は、ユーザーに対して Skype for Business Server アーカイブポリシーを構成する必要はありません。 代わりに、exchange を使用しているユーザーのアーカイブをサポートするように Exchange のインプレースホールドポリシーを構成します。メールボックスは、インプレースホールドに配置されています。 これらのポリシーの構成の詳細については、Exchange の製品に関するドキュメントを参照してください。
    
- 展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合は、Skype for Business Server のアーカイブデータベース (SQL Server データベース) をトポロジに追加し、更新されたトポロジを公開して、アーカイブポリシーを設定する必要があります。ユーザーの設定。 アーカイブ データベースの展開は、初期トポロジの展開と同時か、または少なくとも 1 つのフロントエンド プールまたは Standard Edition サーバーを展開した後に、行うことができます。 このドキュメントでは、既存の展開に追加することでアーカイブ データベースを展開する方法について説明します。
    
1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にする必要があります。その理由は、通信のアーカイブが必要なユーザーは、別のプールでホストされるグループ IM 会話や会議に招待される可能性があるからです。会話や会議がホストされているプールでアーカイブが有効になっていない場合は、セッション全体をアーカイブすることはできません。このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルや会議参加または退出イベントはアーカイブできません。
  
> [!IMPORTANT]
> コンプライアンスのためにアーカイブが重要である場合は、アーカイブを展開し、ポリシーとその他のオプションを適切なレベルで構成して、適切なユーザー全員のアーカイブを有効にしてから、これらのユーザーを Skype for Business で有効にする必要があります。Business Server。 
  
次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。
  
|**段階**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |Microsoft Exchange の統合 (一部またはすべてのユーザーのアーカイブストレージで Exchange を使用) を使用するには、既存の Exchange の展開が必要です。  <br/> 一部またはすべてのユーザーのストレージをアーカイブするために別のアーカイブ データベースを使用するには (SQL Server データベースを使用する場合)、アーカイブ データを格納するサーバーに SQL Server が必要です。  <br/> アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Skype for Business と Exchange の統合の計画](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Skype for Business Server 2019 のシステム要件](../../../SfBServer2019/plan/system-requirements.md) |
|**アーカイブをサポートする適切な内部トポロジを作成します (展開のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合のみ)。** <br/> |トポロジビルダーを実行して、Skype for Business Server のアーカイブデータベース (SQL Server データベース) をトポロジに追加し、次にトポロジを公開します。  <br/> |アーカイブ データベースを組み込むためのトポロジを定義する場合は、ローカル ユーザー グループのメンバーであるアカウント。  <br/> トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Skype for Business Server ファイルストアで使用されるファイル共有に対してフルコントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーは、必要な Dacl を構成できます。  <br/> |[Skype for Business Server の既存の展開にアーカイブデータベースを追加する](add-archiving-databases.md) <br/> |
|**サーバー間認証を構成する (Microsoft Exchange 統合を使用している場合のみ)** <br/> |Skype for Business Server と Exchange の間の認証を有効にするようにサーバーを構成します。 アーカイブを有効にする前に、 **CsExchangeStorageConnectivity testuser_sipUri の収集**機能を実行して、Exchange アーカイブストレージの接続を検証することをお勧めします。 <br/> |サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。  <br/> |サーバー間認証の管理  <br/> |
|**アーカイブのオプションとポリシーの構成** <br/> |Microsoft Exchange 統合を使用するかどうか、グローバルポリシー、サイトとユーザーのポリシー (すべてのデータストレージに対して Microsoft Exchange の統合を使用していない場合)、および重要なモードやデータなどの特定のアーカイブオプションを含むアーカイブを構成します。エクスポートと削除。  <br/> Microsoft Exchange 統合を使用している場合は、必要に応じて、Exchange のインプレースホールドポリシーを構成します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。または、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。  <br/> |[Skype for Business Server のアーカイブオプションを構成する](configure-archiving-options.md) <br/> Exchange 製品ドキュメント (Microsoft Exchange 統合を使用している場合)。  <br/> |
   

