---
title: デバイス ログの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データのキャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前に保持される時間の長さに関するしきい値を設定できます。 これらの設定は、組織の要件に従って変更できます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: 118f2e6d90e9c3f7559a5e129c844ccdf1ea9bf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830337"
---
# <a name="device-log-configuration"></a>デバイス ログの構成

デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データのキャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前に保持される時間の長さに関するしきい値を設定できます。 これらの設定は、組織の要件に従って変更できます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。

> [!NOTE]
> デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。 この設定は、Skype for Business Server コントロール パネルを使用して変更することはできません。 代わりに、Skype for Business Server 管理シェルを使用する必要があります。 期限切れのログ ファイルを削除する時刻を指定するには **、New-CsDeviceUpdateConfiguration** コマンドレットに -LogCleanUpTimeOfDay パラメーターを指定して使用します。 詳細については [、「New-CsDeviceUpdateConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> ファイルを削除すると、それらはファイル システムから完全に削除されます。 ファイルを削除した後、ファイルを復旧することはできません。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**デバイス ログの構成**] ページでは、次のタスクを実行できます。

- グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。

- 既存のデバイス ログ構成のオプションを変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **新規** 次のスコープで新しいデバイス ログ構成を追加できます。

  - グローバル

  - Site

- **編集** 一覧のデバイス ログ構成のオプションを変更できます。 このオプションを使用すると、次の操作を実行できます。

  - **詳細の表示** このオプションを選択すると、デバイス ログ構成のオプションを変更できるダイアログ ボックスが開きます。

  - **すべて選択** このオプションは、一覧内のすべてのデバイス ログ構成を選択します。

  - **削除** このオプションを選択すると、選択したデバイス ログ構成はすべて削除されます。

- **更新** デバイス ログ構成リストを更新して、すべてのデバイス ログ構成のオプションの状態を確認できます。

## <a name="see-also"></a>関連項目

[デバイス更新アクティビティのログ ファイルの設定の変更](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
