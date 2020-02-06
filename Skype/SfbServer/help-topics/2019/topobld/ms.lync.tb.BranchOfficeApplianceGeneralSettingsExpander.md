---
title: ブランチ オフィス アプライアンス全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 既存の Survivable Branch Appliance または Survivable ブランチサーバーの設定を編集するには、次のセクションが表示されます。
ms.openlocfilehash: 262a4c54b571d0b0232a66d0f996af96931515b1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793905"
---
# <a name="branch-office-appliance-general-settings-expander"></a>ブランチ オフィス アプライアンス全般設定エキスパンダー

既存の Survivable Branch Appliance または Survivable ブランチサーバーの設定を編集するには、次のセクションが表示されます。

- 全般設定

- 復元の設定

- 仲介サーバーの設定


Survivable Branch Appliance または Survivable ブランチサーバーの場合、次の内容が表示されます。

### <a name="general-settings"></a>全般設定

Survivable Branch Appliance または Survivable ブランチサーバーの完全修飾ドメイン名 (FQDN)。 値を変更するには、サーバーの FQDN を編集します。 新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。

[**すべての構成済み IP アドレスを使用する**] または [**サービスの使用を選択した IP アドレスに限定する**] を選択できます。[**サービスの使用を選択した IP アドレスに限定する**] を選択する場合、公衆交換電話網 (PSTN) ゲートウェイを除くすべての通信にサーバーが使用するプライマリ IP アドレスを定義します。PSTN 使用には、別の IP アドレスを定義します。

[**関連付け**] では、次の情報を編集または指定できます。

- [アーカイブサーバーの関連付け] を選択すると、アーカイブサーバーを Survivable Branch Appliance または Survivable Branch Server に関連付けることができます。 ドロップダウンリストからサーバーを選ぶか、[**新規**] をクリックして新しいアーカイブサーバーを指定して、既に定義されたアーカイブサーバーから選ぶことができます。

    > [!IMPORTANT]
    > 新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。

- [監視サーバーの関連付け] では、監視サーバーを Survivable Branch Appliance または Survivable Branch Server に関連付けることができます。 ドロップダウンリストからサーバーを選ぶか、[**新規**] をクリックして、新しい監視サーバーを指定して、既に定義されている監視サーバーから選ぶことができます。

- [Edge プールの関連付け] を選択すると、エッジサーバーまたはプールを Survivable Branch Appliance または Survivable Branch Server に関連付けることができます。 ドロップダウン リストからサーバーを選択して定義済みのエッジ サーバーやプールから選択するか、[**新規**] をクリックして新しいエッジ サーバーやプールを指定できます。

### <a name="resiliency"></a>復元

復元により、レジストラー プールの可用性を高めることができます。バックアップ レジストラーを指定することで、プライマリ レジストラーに障害が発生した場合、障害が発生したレジストラーの処理をバックアップ レジストラーが引き継ぐため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムに応じて、ユーザーの機能性が低下する可能性があります。

ドロップダウンリストから、Survivable Branch Appliance または Survivable Branch Server のバックアップレジストラーとして機能する Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーを選びます。 フェールオーバーまたは代替の時間間隔を有効にする設定を選択することもできます。 フェールオーバーとフォールバックの時間設定 (秒単位で指定) を有効にすることにより、障害が発生したレジストラーを自動検出し、プライマリ レジストラーが回復してレジストラー プロセスを引き継ぎ可能になったことを自動的に判定するためのフォールバック時間を確保できます。

> [!IMPORTANT]
> 障害検出とフォールバックの間隔を定義する場合は、レジストラーが短時間応答しなかった場合にフェールオーバーとフォールバックが発生するような間隔を入力しないよう注意してください。 プライマリ レジストラーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。 サイト内の Survivable Branch Appliance または Survivable Branch Server の既定値は、1つのプールまたは標準エディションのフロントエンドサーバーに対する120秒のフェールオーバーおよび240秒です。

### <a name="mediation-server"></a>仲介サーバー

[**仲介サーバー**] では、次の情報を指定できます。

仲介サーバーが併置されているため、Survivable Branch Appliance または Survivable Branch Server では、併置され**ている仲介サーバー**のチェックボックスは使用できません。

トランスポート層セキュリティ (TLS) のプールサーバーでリッスンポートを定義します。 既定では、このポートは5067です。 [ **Tcp ポートを有効に**する] を選択した場合は、併置された仲介サーバーの tcp ポートを定義する必要があります。 これはオプションの設定であり、必要に応じてゲートウェイまたは PSTN の要件を確認する必要があります。 既定では、[TCP ポート] の値は5068です。

併置された仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。 既にゲートウェイが定義されている場合は、それらを仲介サーバーと関連付けることができます。 ゲートウェイを定義していない場合に定義可能なゲートウェイが存在するときは、[**新規**] を選択できます。 この仲介サーバーに既に構成されているゲートウェイを削除することもできます。 ゲートウェイを選択して、[**削除**] をクリックします。

仲介サーバーと関連付けられているゲートウェイが複数ある場合は、最初に関連付けられたゲートウェイが既定のゲートウェイになります。 別のゲートウェイをデフォルト ゲートウェイとして選択する必要がある場合は、デフォルトにするゲートウェイを選択して、[**デフォルトに設定**] をクリックします。


Survivable Branch Appliance または Survivable ブランチサーバーの設定の定義と構成の詳細については、「[ブランチサイトの回復性ソリューション](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)」を参照してください。


