---
title: 展開設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 次のセクションを使用して、既存の展開のプロパティを編集できます。
ms.openlocfilehash: c7a360146f91c2e411ff48f52d92a3c69b0a2e11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835367"
---
# <a name="deployment-settings-expander"></a>展開設定エキスパンダー

次のセクションで、既存の展開のプロパティを編集できます。

- SIP ドメイン

- 簡単な URL

- 中央管理サーバー

## <a name="sip-domain"></a>SIP ドメイン

**[既定の SIP ドメイン]** を編集するには、新しいドメイン名を入力します。

**[追加のサポートされる SIP ドメイン]** を追加するには、追加する必要があるドメインの名前を入力します。 **[追加]** をクリックして、新しいセッション開始プロトコル (SIP) のドメイン名として確定します。

既存の追加の SIP ドメイン名を更新するには、ドメイン名を選択し、テキスト ボックスで変更します。**[更新]** をクリックして変更を確定します。

定義済みの追加の SIP ドメイン名を削除するには、ドメイン名を選択し、[削除] をクリック **します**。

[プロパティの編集] ページですべての変更が完了したら、**[OK]** をクリックして変更を保存します。変更を破棄するには、**[キャンセル]** をクリックします。

## <a name="simple-urls"></a>簡単な URL

簡単な URL を変更または定義するには、3 種類の簡単な URL の中から編集または変更する URL を決めます。[電話アクセスの URL]、[ミーティング URL]、および [管理アクセスの URL] から選択できます。

[電話アクセスの URL] または [ミーティング URL] を変更するには、変更が必要な URL を選択します。 **[URL の編集]** をクリックします。 URL を編集し、**[OK]** をクリックして URL を保存します。 変更をすべて破棄する場合は、[**キャンセル**] をクリックします。

新しい URL を追加するには、**[追加]** をクリックします。 **[簡単な URL の追加]** ダイアログで、URL を指定し、**[OK]** をクリックして URL を保存します。 新しい URL をアクティブな URL として設定する必要がある場合は、**[これを選択したドメインのアクティブな URL にする]** を選択します。 変更をすべて破棄する場合は、[**キャンセル**] をクリックします。

別の URL をアクティブな URL (URL の横にある緑色のチェックマークで示されている) にするには、URL を選択し、[アクティブにする] を **クリックします**。

> [!NOTE]
> アクティブな URL は SIP ドメインごとに 1 つしか使用できます。

URL を削除する必要がある場合は、URL を選択し、**[削除]** をクリックします。

> [!CAUTION]
> 簡易 URL 設定ダイアログ ページの情報を注意深く読んでください。 会議 URL を削除すると、ユーザーによってスケジュールされた会議にアクセスできなくなる可能性があります。 新しい会議 URL をアクティブにした後は、以前の URL を残してください。 ユーザーが古い会議 URL を使用しない場合は、その URL を安全に削除できます。

管理アクセスの URL を編集または変更するには、エントリを編集します。

[プロパティの編集] ページですべての変更が完了したら、**[OK]** をクリックして変更を保存します。変更を破棄するには、**[キャンセル]** をクリックします。

## <a name="central-management-server"></a>中央管理サーバー

中央管理サーバーを、ある定義済みのフロントエンドのプールから別の定義済みのフロントエンドのプールに変更できます。中央管理サーバーの場所を変更するには、[**中央管理サーバーをインストールするフロントエンド サーバー**] の下のドロップダウン リストからフロントエンド プールを選択します。フロントエンド サーバーは、Enterprise Edition フロントエンドのプールまたは Standard Edition フロントエンド サーバーのいずれかにできます。

> [!IMPORTANT]
> インフラストラクチャの中央管理ストアを定義、発行、および展開した後は、外部プロセスによって中央管理ストアを別のフロントエンドに再配置せずに中央管理ストアの場所を変更することはできません。

中央管理ストアの移動の詳細については、次のコマンドレット リファレンスの [「Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) Windows PowerShell参照してください。

## <a name="see-also"></a>関連項目

これらの設定の定義と構成の詳細については、「[Defining and Configuring the Topology (トポロジの定義と構成)](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)」を参照してください。


