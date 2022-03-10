---
title: Microsoft Teams のエンドツーエンド暗号化
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 03/08/2022
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Microsoft Teams の強化された暗号化機能について説明し、Teams 管理センターと Microsoft PowerShell を使用してエンドツーエンドの暗号化を管理します。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 202aee527896b331a6c8e64e1fc8736fa4942ecb
ms.sourcegitcommit: fe71ecbe35b8adfb9166188923ed1111b3b8e2a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63388191"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls"></a>1 対 1 の Microsoft Teams 通話にエンドツーエンドの暗号化を使用する

> [!IMPORTANT]
> Teams サービス モデルと暗号化サポートは、カスタマー エクスペリエンスを向上させるために変更される可能性があります。 たとえば、このサービスは、セキュリティで保護されなくなった暗号スイートを定期的に非推奨にします。 このような変更は、Teams の安全性と設計による高い信頼性を保つことを目的に行われます。 さらに、Microsoft データ センター内のすべてのカスタマー コンテンツは暗号化されます。 Microsoft 365 の暗号化レイヤーの詳細については、「[Microsoft 365 の暗号化](/microsoft-365/compliance/encryption)」を参照してください。

エンド ツー エンド暗号化 (E2EE) は、コンテンツが送信される前に暗号化され、意図していた受信者によってのみ復号化された場合にのみ発生します。 エンドツーエンドの暗号化では、2 つのエンドポイント システムのみが通話データの暗号化と復号化に関与します。 マイクロソフトを含む他の当事者は、復号化された会話にアクセスできません。

予定外の 1 対 1 の通話用の E2EE を使用すると、1 対 1 の Teams 通話のリアルタイム メディア フロー (ビデオと音声データ) のみがエンドツーエンドで暗号化されます。 エンドツーエンドの暗号化を有効にするには、この設定をオンにする必要があります。 [Microsoft 365 の暗号化](/microsoft-365/compliance/encryption)は、通話内のチャット、ファイル共有、プレゼンス、およびその他のコンテンツを保護します。

エンドツーエンドの暗号化を有効にしない場合でも、Teams は業界標準に基づく暗号化を使用して通話や会議をセキュリティで保護します。 通話中に交換されるデータは、転送中および保存中は常に安全です。 詳細については、「[Teams のメディアの暗号化](teams-security-guide.md#media-encryption)」を参照してください。

エンドツーエンドの暗号化された通話中に、Teams は次の機能を保護します。

- オーディオ

- ビデオ

- 画面共有

E2EE 通話中は、次の高度な機能を使用できません。

- ライブ キャプションと文字起こし

- 呼び出し転送

- 呼び出しのマージ

- コール パーク

- 確認して転送

- コンパニオンに電話して別のデバイスに転送する

- 参加者の追加

- 記録

また、組織でコンプライアンス レコーディングを使用している場合、エンドツーエンドの暗号化は使用できません。 Teams がコンプライアンス レコーディングをサポートする方法の詳細については、「[通話と会議用の Teams ポリシーベースのレコーディングの概要](teams-recording-policy.md)」を参照してください。

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Microsoft Teams のエンドツーエンドの暗号化を構成する

これらのタスクを完了して、ユーザーがエンドツーエンドの暗号化された通話を実行できるようにします。

- エンドツーエンドの暗号化を使用できるユーザーを定義する 1 つ以上のポリシーを作成して、組織のエンドツーエンドの暗号化を有効にします。 開始する前に、職場または学校アカウントに Teams またはグローバル管理者ロールが割り当てられていることを確認します。 詳細については、「[Microsoft Teams 管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。 E2EE を設定する準備ができたら、Teams 管理センターまたは Microsoft PowerShell を使用できます。

- デバイスの Teams 設定で、エンドツーエンドの暗号化された通話をオンにします。 各ユーザーはこのタスクを完了する必要がありますが、1 つのデバイスでのみ実行する必要があります。 Teams は、ユーザーごとにサポートされているエンドポイント間でこの設定を同期します。 手順については、「[Teams 通話用のエンドツーエンド暗号化を使用する](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)」を参照してください。

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Teams 管理センターを使用してエンドツーエンドの暗号化を構成する

組織全体の既定のグローバル ポリシーでは、エンドツーエンドの暗号化を無効にすることを指定します。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 エンドツーエンドの暗号化を有効にするには、新しい暗号化ポリシーを作成するか、グローバルな既定のポリシーを変更します。 Teams 管理センターを使用してエンドツーエンドの暗号化を有効にするには、次の手順を実行します。

1. Teams またはグローバル管理者ロールが割り当てられている職場または学校アカウントを使用して、[Teams 管理センター](https://admin.teams.microsoft.com/)にサインインします。

2. **[その他の設定]、** > **[強化された暗号化ポリシー]** の順に移動します。

3. 既定のポリシーを選択するか **[追加]** を選択して新しいポリシーを追加し、新しいポリシーに名前を付けます。

4. ユーザーに対してエンド ツー エンドの暗号化を有効にするには、**[エンド ツー エンドの呼び出しの暗号化]**、**[ユーザーが有効にできる**] を選択し、**[保存]** を選択します。

   エンドツーエンドの暗号化を無効にするには、**[すべてのユーザーに対してオフにする]** を選択します。

ポリシーの設定が完了したら、他の Teams ポリシーを管理するのと同じ方法で、ユーザー、グループ、またはテナント全体にポリシーを割り当てます。 Teams でポリシーを使用する方法については、「[ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)」を参照してください。

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Microsoft PowerShell を使用してエンドツーエンドの暗号化を構成する

Microsoft PowerShell と Teams 管理センターを使用して、エンドツーエンドの暗号化ポリシーを管理できます。 Teams PowerShell モジュールには、エンドツーエンドの暗号化コマンドレットがいくつか含まれており、「[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps&preserve-view=true)」に記載されています。 この記事では、使用できるコマンドレットのリストと、簡単な構成例を示します。 これらの構成では、既定のグローバル ポリシーが使用されます。 組織では、より複雑なポリシー構成が必要になる場合があります。 これらのコマンドレットの詳細については、コマンドレット リファレンスに記載されています。

エンドツーエンドの暗号化 PowerShell コマンドレット:

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) は、組織内の Teams の強化された暗号化ポリシーに関する情報を返します。

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) は、既存の強化された暗号化ポリシーをユーザーに割り当てたり割り当てを解除したりします。 ユーザーからすべてのポリシーの割り当てを解除するには、`$NULL` を使用します。

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) は、新しい Teams の強化された暗号化ポリシーを作成します。

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) は、強化された暗号化ポリシーを組織から削除します。 グローバルな既定のポリシーは削除できません。

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) は、既存の Teams の強化された暗号化ポリシーの値を更新します。

エンドツーエンドの暗号化を構成するには、職場または学校アカウントに Teams またはグローバル管理者の役割が必要です。

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>グローバル ポリシーを使用してテナント全体のエンドツーエンド暗号化を有効にするには

既定では、エンドツーエンドの暗号化は無効になっています。既定のグローバル ポリシーを設定してテナント全体のエンドツーエンドの暗号化を有効にするには、次のように [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) コマンドレットを実行します。

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

詳細は次のとおりです。

- `Global` は、組織全体の既定のグローバル ポリシーでこの構成を設定していることを意味します。

- `DisabledUserOverride` は、既定では Teams で E2EE が無効になっていますが、ユーザーは既定を上書きし、Teams の設定で E2EE を有効にできることを意味します。

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>グローバル ポリシーを使用してテナント全体のエンドツーエンド暗号化を無効にするには

既定では、エンドツーエンドの暗号化は無効になっています。グローバル ポリシーに変更を加えた場合は、次のように [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) コマンドレットを実行して、設定を元に戻すことができます。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

詳細は次のとおりです。

- `Global` は、組織全体の既定のグローバル ポリシーでこの構成を設定していることを意味します。

- `Disabled` は、すべてのユーザーに対して E2EE を無効にしており、ユーザーが Teams の設定で有効にできないことを意味します。

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>1 人のユーザーに対してエンド ツー エンドの暗号化を有効にするには

ユーザーのエンドツーエンド暗号化を有効にするには、次のように [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) コマンドレットを実行します。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

詳細は次のとおりです。

- *`username`* はユーザーの名前です。

- *`policyname`* はポリシーに使用する名前です。 ポリシー名にスペースを含めることはできません (ContosoE2EEUserPolicy など)。

ユーザーは、エンドツーエンドの暗号化された通話を行う前に、Teams の設定でエンドツーエンドの暗号化された通話をオンにする必要があります。手順については、「[Teams 通話用のエンドツーエンド暗号化を使用する](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)」を参照してください。

次に例を示します。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>単一ユーザーからエンドツーエンドの暗号化ポリシーの割り当てを解除するには

ユーザーは、一度に 1 つだけの暗号化ポリシーを割り当てることができます。 ユーザーからポリシーの割り当てを解除すると、ユーザーにはグローバルな組織全体の既定のポリシーが割り当てられます。 既定のポリシーの割り当てを解除することはできません。 ユーザーからエンドツーエンドの暗号化ポリシーの割り当てを解除するには、次のように [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) コマンドレットを実行します。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>デバイスでエンドツーエンドの暗号化をオンにする

手順については、「[Teams 通話用のエンドツーエンド暗号化を使用する](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)」を参照してください。

## <a name="related-topics"></a>関連項目

[Top 12 tasks for security teams to support working from home](/microsoft-365/security/top-security-tasks-for-remote-work) (在宅勤務をサポートするためにセキュリティ チームが行う 12 の主なタスク)

[Microsoft Teams で会議の設定を管理する](./meeting-settings-in-teams.md)
