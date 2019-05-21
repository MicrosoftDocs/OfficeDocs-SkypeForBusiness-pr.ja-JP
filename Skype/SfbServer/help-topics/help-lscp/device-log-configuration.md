---
title: デバイス ログの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一部として、ログデータキャッシュサイズ、ログファイルサイズ、またはログファイルが削除されるまでの一定期間のしきい値を設定することができます。 組織の要件に応じて、これらの設定を変更することができます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: e46811d40a7b93f5c59557c6744fb554b70aea2a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285940"
---
# <a name="device-log-configuration"></a>デバイス ログの構成

デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一部として、ログデータキャッシュサイズ、ログファイルサイズ、またはログファイルが削除されるまでの一定期間のしきい値を設定することができます。 組織の要件に応じて、これらの設定を変更することができます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。

> [!NOTE]
> デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。 この設定は、Skype for Business Server コントロールパネルを使用して変更することはできません。 代わりに、Skype for Business Server 管理シェルを使用する必要があります。 有効期限が切れたログファイルを削除する時刻を指定するには、-LogCleanUpTimeOfDay パラメーターを指定して、**新しい-CsDeviceUpdateConfiguration**コマンドレットを使用します。 詳しくは、「[新しい-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)方法」をご覧ください。

> [!CAUTION]
> ファイルを削除すると、ファイル システムから完全に削除されます。ファイルを削除した後に復旧することはできません。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**デバイス ログの構成**] ページでは、次のタスクを実行できます。

- グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。

- 既存のデバイス ログ構成のオプションを変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **新規**次のスコープを持つ新しいデバイスログ構成を追加できます。

  - グローバル

  - サイト

- **編集**一覧のデバイスログ構成のオプションを変更できます。 このオプションを使うと、次の操作を行うことができます。

  - **詳細を表示**このオプションを選択すると、デバイスログ構成のオプションを変更できるダイアログボックスが表示されます。

  - **すべて選択**このオプションでは、一覧にあるすべてのデバイスログの構成が選択されます。

  - **削除**このオプションは、選択したすべてのデバイスログ構成を削除します。

- **更新**デバイスログの構成の一覧を更新して、すべてのデバイスログ構成のオプションの状態を確認できます。

## <a name="see-also"></a>関連項目

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
