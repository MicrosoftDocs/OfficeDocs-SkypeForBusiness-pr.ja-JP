---
title: Teams 会議のカスタム会議の背景
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: バックグラウンドなどの承認済みの企業資産を使用して、組織内の Teams 会議のカスタム背景を作成します。
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800224"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Teams 会議のカスタム会議の背景

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>概要

Teams 会議でのカスタマイズにより、組織は会議エクスペリエンス全体でビジュアル ID を拡張できます。 カスタム会議の背景を使用すると、社内の企業文化の構築を促進し、社内および外部の会議参加者の両方で全体的なブランドの認識を高めるのに役立ちます。 組織のブランド管理チームと企業コミュニケーション チームの助けを借りて、管理者は、1 つのテナント内のさまざまな部署や部署のカスタム会議の背景を簡単に設定して作成できます。

既定では、管理者であるか、会議のカスタマイズ ポリシーが割り当てられている Teams Premium ライセンスユーザーは、カスタム会議の背景を備えた会議を作成できます。 これらのカスタム 背景は、Teams Premium ライセンスを持つ組織内のエンド ユーザーのみが使用できます。

## <a name="prerequisites"></a>前提条件

Teams 会議のカスタム会議の背景を設定する前に、次の項目があることを確認します。

- Teams Premium SKU へのアクセス
- Teams 管理センターにアクセスできる管理者であるか、カスタマイズ ポリシーが割り当てられている
- [カスタム バックグラウンド ポリシー](#enabling-the-custom-background-policy)を有効にしました
- 背景イメージが[必要な仕様](#adding-custom-background-images)を満たしている

## <a name="setting-up-custom-meeting-backgrounds"></a>カスタム会議の背景を設定する

管理者は、Teams 管理センターで Teams 会議のカスタム会議の背景をアップロードおよび管理できます。

### <a name="enabling-the-custom-background-policy"></a>カスタム バックグラウンド ポリシーの有効化

管理者は、カスタム背景を作成するには、新しい会議カスタマイズ ポリシーを作成するか、組織のグローバル既定ポリシーを変更する必要があります。
カスタム バックグラウンド ポリシーを有効にするには、管理者は次の手順を実行します。

1. Teams 管理センターを開く
2. ナビゲーション ウィンドウから [ **会議** ] を選択します
3. [会議] で、カスタム バックグラウンド ポリシーにアクセスするには 2 つの方法があります。 **[カスタマイズ ポリシー**] を選択して既存のポリシーを選択するか、新しいポリシーを作成できます。 または、[ **会議ポリシー** ] を選択し、右上隅にある [ **カスタム会議画像** ] ボタンを選択することもできます。
4. 選択したポリシー内で、[ **カスタム会議の背景** ] セクションに移動します
5. **[カスタム 背景**] 設定をオフからオンに切り替えて、設定を有効にします
6. [ **保存] を選択します**

### <a name="adding-custom-background-images"></a>カスタム背景画像の追加

カスタムバックグラウンドポリシーを有効にしたので、カスタム背景画像をアップロードできます。 これらのイメージは、アップロード時に順序付けされたエンド ユーザーのインターフェイスに表示されます。

アップロードは、次のパラメーターに従う必要があります。 管理者は次をアップロードできます。

- 画像の PNG および JPEG 画像形式
- 最小サイズが 360 px X 360 px の画像
- 最小寸法が 3840 px X 2160 px の画像
- 最大 50 個のカスタム背景画像

画像をアップロードするには、[ **会議** > **のカスタマイズ ポリシー]** に移動し、前の手順からポリシーを選択します。 [ **カスタム会議の背景** ] セクションまで下にスクロールし、カスタム背景のトグルが表示されているテーブルの下にある [ **+追加**] を選択します。 [+追加] を選択すると、[ **背景の管理** ] というウィンドウが開き、画像を追加できます。

> [!NOTE]
> Teams Premium ライセンスを持つエンド ユーザーのみが、[バックグラウンド設定] パネルにこれらの画像を表示します。

### <a name="saving-custom-background-images"></a>カスタム背景画像の保存

アップロードした画像のプレビューは、新しいテーブルの [ **カスタム会議の背景** ] セクションにあります。 この表には、イメージの名前と解像度も表示されます。 アップロードした画像の選択を確認したら、プレビュー テーブルの下にある **[保存** ] ボタンを選択します。 [保存] を選択したので、アップロードした背景は、Teams Premium ライセンスを持つエンド ユーザーに表示されます。

## <a name="where-are-custom-backgrounds-visible"></a>カスタム背景が表示される場所

次の一覧には、カスタム 背景が表示されるサポートされているクライアントが表示されます。

- Web クライアント
- デスクトップ クライアント
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>カスタム会議の背景を選択して適用できるユーザー

[バックグラウンド設定] パネルで会議の背景を使用できるのは、ライセンスを持つユーザー Teams Premiumだけです。

> [!NOTE]
> 外部ユーザーまたは匿名ユーザーは、カスタム会議の背景を使用できません。

### <a name="who-can-view-custom-meeting-backgrounds"></a>カスタム会議の背景を表示できるユーザー

ライセンスを持つエンド ユーザーのみがアップロードされた背景の選択を選択できますが、会議に適用されている背景は誰でも表示できます。 これらのユーザーには、次のものが含まれます。

- テナント内、Teams Premiumライセンスを持つユーザー
- テナント内ユーザー、非ライセンス ユーザー
- 外部ユーザー
- 匿名ユーザー
