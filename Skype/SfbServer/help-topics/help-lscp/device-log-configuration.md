---
title: デバイス ログの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データ キャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前にログ ファイルを保持する時間の長さにしきい値を設定できます。 これらの設定は、組織の要件に従って変更できます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: b20c7bb088f46491c99ada7c815b8c11d4bfe456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115285"
---
# <a name="device-log-configuration"></a>デバイス ログの構成

デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データ キャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前にログ ファイルを保持する時間の長さにしきい値を設定できます。 これらの設定は、組織の要件に従って変更できます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。

> [!NOTE]
> デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。 この設定は、Skype for Business Server コントロール パネルを使用して変更できません。 代わりに、Skype for Business Server 管理シェルを使用する必要があります。 期限切れのログ ファイルを削除する時刻を指定するには、-LogCleanUpTimeOfDay パラメーターと一緒に **New-CsDeviceUpdateConfiguration** コマンドレットを使用します。 詳細については [、「New-CsDeviceUpdateConfiguration」を参照してください](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> ファイルを削除すると、それらはファイル システムから完全に削除されます。 ファイルを削除した後、ファイルを復旧することはできません。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**デバイス ログの構成**] ページでは、次のタスクを実行できます。

- グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。

- 既存のデバイス ログ構成のオプションを変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **New** 次のスコープで新しいデバイス ログ構成を追加できます。

  - グローバル

  - サイト

- **編集** リスト内のデバイス ログ構成のオプションを変更できます。 このオプションを使用すると、次の操作を実行できます。

  - **詳細の表示** このオプションは、デバイス ログ構成のオプションを変更できるダイアログ ボックスを開きます。

  - **[すべて選択]** このオプションは、リスト内のすべてのデバイス ログ構成を選択します。

  - **削除** このオプションは、選択したデバイス ログ構成をすべて削除します。

- **更新** デバイス ログ構成リストを更新して、すべてのデバイス ログ構成のオプションの状態を確認できます。

## <a name="see-also"></a>関連項目

[デバイス更新アクティビティのログ ファイルの設定の変更](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)