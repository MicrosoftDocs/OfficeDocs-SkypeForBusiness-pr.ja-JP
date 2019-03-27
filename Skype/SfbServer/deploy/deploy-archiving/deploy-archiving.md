---
title: Skype ビジネス サーバーのアーカイブを展開します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '概要: は、Skype のビジネス サーバーのアーカイブを展開する方法については、このトピックを読みます。'
ms.openlocfilehash: 0598d1a35523cc38d85320206b065b85e025687e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895070"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Skype ビジネス サーバーのアーカイブを展開します。
 
**の概要:** Skype ビジネス サーバーのアーカイブを展開する方法の詳細については、このトピックを参照してください。
  
ビジネス サーバーの展開、Skype でのそれぞれのフロント エンド サーバーに自動的にインストールは、アーカイブが、それを使用する前に、最初のセットアップと構成の手順を実行する必要があります。 作業を開始する前に、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)の概念に精通していることを確認します。
  
## <a name="deployment-checklist"></a>展開チェックリスト

アーカイブのセットアップ方法は、選択するストレージ オプションによって異なります。 
  
- 配置内のすべてのユーザーの Microsoft Exchange の統合を使用する場合、ユーザーのアーカイブ ・ ポリシーをビジネス サーバー用 Skype を構成する必要はありません。 代わりに、インプレース保持に自分のメールボックスに、exchange の置かれているユーザー用にアーカイブをサポートするための Exchange インプレース保持ポリシーを構成します。 これらのポリシーの構成に関する詳細については、Exchange 製品のマニュアルを参照してください。
    
- 配置内のすべてのユーザーの Microsoft Exchange の統合を使用しない場合必要があります Skype をビジネスのサーバー トポロジ、データベース (SQL Server データベース) をアーカイブに追加するのには、更新されたトポロジを公開して、アーカイブ ・ ポリシーを構成し、ユーザーに設定します。 アーカイブ データベースの展開は、初期トポロジの展開と同時か、または少なくとも 1 つのフロントエンド プールまたは Standard Edition サーバーを展開した後に、行うことができます。 このドキュメントでは、既存の展開に追加することでアーカイブ データベースを展開する方法について説明します。
    
1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にする必要があります。その理由は、通信のアーカイブが必要なユーザーは、別のプールでホストされるグループ IM 会話や会議に招待される可能性があるからです。会話や会議がホストされているプールでアーカイブが有効になっていない場合は、セッション全体をアーカイブすることはできません。このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルや会議参加または退出イベントはアーカイブできません。
  
> [!IMPORTANT]
> アーカイブのコンプライアンス上の理由から、組織の重要な場合は、アーカイブを展開する、適切なレベルでは、ポリシー、およびその他のオプションを構成して後の Skype のユーザーを有効にする前にすべての適切なユーザーのアーカイブを有効にしてください。ビジネス サーバーです。 
  
次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。
  
|**段階**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |(Exchange のいくつかまたはすべてのユーザーのアーカイブ ・ ストレージを使用して)、Microsoft Exchange の統合を使用するには、既存の Exchange の展開が必要です。  <br/> 一部またはすべてのユーザーのストレージをアーカイブするために別のアーカイブ データベースを使用するには (SQL Server データベースを使用する場合)、アーカイブ データを格納するサーバーに SQL Server が必要です。  <br/> アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Skype for Business と Exchange の統合の計画](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[ビジネス サーバー 2019 Skype のシステム要件](../../../SfBServer2019/plan/system-requirements.md) |
|**(場合にのみ、配置内のすべてのユーザーに対して、Microsoft Exchange の統合を使用していない) のアーカイブをサポートするために適切な内部トポロジを作成します。** <br/> |このトポロジでは、Skype をビジネスのサーバー (SQL Server データベース) のデータベースをアーカイブに追加するのにはトポロジ ビルダーを実行し、トポロジを公開し、します。  <br/> |アーカイブ データベースを組み込むためのトポロジを定義する場合は、ローカル ユーザー グループのメンバーであるアカウント。  <br/> ビジネス サーバーのファイル ストアの Skype に使用するファイル共有のトポロジでは、RTCUniversalServerAdmins グループ、domain admins グループのメンバーであるし、フル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウントを発行する (ようにトポロジビルダーが Dacl を構成、必要な)。  <br/> |[Skype で既存の展開にビジネスのサーバーにアーカイブ データベースを追加します。](add-archiving-databases.md) <br/> |
|**(Microsoft Exchange の統合を使用する) 場合のみ、サーバーからサーバーへの認証を構成します。** <br/> |Skype ビジネス サーバーと Exchange との間の認証を有効にするサーバーを構成します。 実行することをお勧め**テスト CsExchangeStorageConnectivity testuser_sipUri-フォルダーのごみ箱をあさる**Exchange のストレージへの接続のアーカイブを有効にする前にアーカイブを検証します。 <br/> |サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。  <br/> |サーバー間認証の管理  <br/> |
|**アーカイブのオプションとポリシーの構成** <br/> |アーカイブには、Microsoft Exchange の統合、グローバル ポリシー、サイト ポリシーとユーザー ポリシー (すべてのデータ ・ ストレージの Microsoft Exchange の統合を使用していない) 場合を使用するかどうかなど、特定のアーカイブを構成する重要なモードやデータなどのオプションエクスポートおよび削除します。  <br/> Microsoft Exchange の統合を使用している場合は、必要に応じて Exchange インプレース保持ポリシーを構成します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。または、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。  <br/> |[Skype のビジネス サーバー用のアーカイブのオプションを構成します。](configure-archiving-options.md) <br/> (Microsoft Exchange の統合を使用する) 場合は、製品のドキュメントを交換します。  <br/> |
   

