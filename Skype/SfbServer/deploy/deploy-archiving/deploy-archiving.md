---
title: Skype for Business Server 2015 のアーカイブの展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '概要: は、Skype のビジネス サーバー 2015 のアーカイブを展開する方法については、このトピックを読みます。'
ms.openlocfilehash: d218c59038b599f016f99cbce453f0bf1830a6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-archiving-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のアーカイブの展開
 
**の概要:**Skype ビジネス サーバー 2015 のアーカイブを展開する方法の詳細については、このトピックを参照してください。
  
アーカイブ サーバー 2015 のビジネス展開に、Skype でのそれぞれのフロント エンド サーバーに自動的にインストールしますが、それを使用する前に、最初のセットアップと構成の手順を実行する必要があります。 作業を開始する前に、 [Skype のビジネス サーバー 2015 でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)の概念に精通していることを確認します。
  
## <a name="deployment-checklist"></a>展開チェックリスト

アーカイブのセットアップ方法は、選択するストレージ オプションによって異なります。 
  
- 配置内のすべてのユーザーの Microsoft Exchange の統合を使用する場合、ユーザーのアーカイブ ・ ポリシーをビジネス サーバー用 Skype を構成する必要はありません。 代わりに、インプレース保持に自分のメールボックスに、exchange の置かれているユーザー用にアーカイブをサポートするための Exchange インプレース保持ポリシーを構成します。 これらのポリシーの構成に関する詳細については、Exchange 製品のマニュアルを参照してください。
    
- 配置内のすべてのユーザーの Microsoft Exchange の統合を使用しない場合必要があります Skype をビジネスのサーバー トポロジ、データベース (SQL Server データベース) をアーカイブに追加するのには、更新されたトポロジを公開して、アーカイブ ・ ポリシーを構成し、ユーザーに設定します。 アーカイブ データベースの展開は、初期トポロジの展開と同時か、または少なくとも 1 つのフロントエンド プールまたは Standard Edition サーバーを展開した後に、行うことができます。 このドキュメントでは、既存の展開に追加することでアーカイブ データベースを展開する方法について説明します。
    
1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にする必要があります。その理由は、通信のアーカイブが必要なユーザーは、別のプールでホストされるグループ IM 会話や会議に招待される可能性があるからです。会話や会議がホストされているプールでアーカイブが有効になっていない場合は、セッション全体をアーカイブすることはできません。このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルや会議参加または退出イベントはアーカイブできません。
  
> [!IMPORTANT]
> アーカイブのコンプライアンス上の理由から、組織の重要な場合は、アーカイブを展開する、適切なレベルでは、ポリシー、およびその他のオプションを構成して後の Skype のユーザーを有効にする前にすべての適切なユーザーのアーカイブを有効にしてください。ビジネス サーバーです。 
  
次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。
  
|**フェーズ**|**手順**|**ロールとグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |(Exchange のいくつかまたはすべてのユーザーのアーカイブ ・ ストレージを使用して)、Microsoft Exchange の統合を使用するには、既存の Exchange の展開が必要です。  <br/> 一部またはすべてのユーザーのストレージをアーカイブするために別のアーカイブ データベースを使用するには (SQL Server データベースを使用する場合)、アーカイブ データを格納するサーバーに SQL Server が必要です。  <br/> アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [ビジネス サーバー 2015 の Skype の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [ビジネス サーバー 2015 の Skype でアーカイブ用のハードウェアおよびソフトウェアの要件](../../plan-your-deployment/archiving/hardware-and-software-requirements.md) <br/> [ビジネスとの交換用 Skype を統合しようとしてください。](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/> |
|**(場合にのみ、配置内のすべてのユーザーに対して、Microsoft Exchange の統合を使用していない) のアーカイブをサポートするために適切な内部トポロジを作成します。** <br/> |このトポロジでは、Skype をビジネスのサーバー (SQL Server データベース) のデータベースをアーカイブに追加するのにはトポロジ ビルダーを実行し、トポロジを公開し、します。  <br/> |アーカイブ データベースを組み込むためのトポロジを定義する場合は、ローカル ユーザー グループのメンバーであるアカウント。  <br/> ビジネス サーバーのファイル ストアの Skype に使用するファイル共有のトポロジでは、RTCUniversalServerAdmins グループ、domain admins グループのメンバーであるし、フル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウントを発行する (ようにトポロジビルダーが Dacl を構成、必要な)。  <br/> |[ビジネス サーバー 2015 の Skype で既存の展開にアーカイブ データベースを追加します。](add-archiving-databases.md) <br/> |
|**(Microsoft Exchange の統合を使用する) 場合のみ、サーバーからサーバーへの認証を構成します。** <br/> |Skype ビジネス サーバーと Exchange との間の認証を有効にするサーバーを構成します。 実行することをお勧め**テスト CsExchangeStorageConnectivity testuser_sipUri-フォルダーのごみ箱をあさる**Exchange のストレージへの接続のアーカイブを有効にする前にアーカイブを検証します。 <br/> |サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。  <br/> |サーバー間認証の管理  <br/> |
|**アーカイブのオプションとポリシーの構成** <br/> |アーカイブには、Microsoft Exchange の統合、グローバル ポリシー、サイト ポリシーとユーザー ポリシー (すべてのデータ ・ ストレージの Microsoft Exchange の統合を使用していない) 場合を使用するかどうかなど、特定のアーカイブを構成する重要なモードやデータなどのオプションエクスポートおよび削除します。  <br/> Microsoft Exchange の統合を使用している場合は、必要に応じて Exchange インプレース保持ポリシーを構成します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。または、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。  <br/> |[ビジネス サーバー 2015 の Skype のアーカイブのオプションを構成します。](configure-archiving-options.md) <br/> (Microsoft Exchange の統合を使用する) 場合は、製品のドキュメントを交換します。  <br/> |
   

