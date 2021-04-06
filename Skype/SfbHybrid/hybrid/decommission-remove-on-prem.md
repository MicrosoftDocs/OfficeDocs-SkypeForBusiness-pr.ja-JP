---
title: Skype for Business Server の使用停止
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Skype for Business Server を使用停止する手順。
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593907"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>オンプレミスの Skype for Business 展開を削除する

この記事では、オンプレミスの Skype for Business 展開を削除する方法について説明します。 これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。

- 手順 1. [必要なすべてのユーザーとアプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。 

- 手順 2. [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- **手順 3.オンプレミスの Skype for Business 展開を削除します。** (この記事)


> [!IMPORTANT] 
> この記事の手順は、ここで説明するように、ユーザー属性の管理に方法 2 を使用している場合にのみ適用 [されます](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。 方法 1 を使用している場合は、この記事で説明されている手順を使用して Skype for Business サーバーを削除しません。 代わりに、サーバーを再イメージできます。

この記事の手順を完了するには、Schema Admins グループと Enterprise Admin グループの両方に対する特権が必要です。 これらの特権は、Skype for Business Server スキーマを元に戻し、Active Directory ドメイン サービスに対するフォレスト レベルの変更を元に戻す必要があります。 RTCUniversalServerAdmins グループのメンバーである必要があります。


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Skype for Business 展開を削除する準備

必要なすべてのユーザー アカウントをクラウドに移動した後も、クリーンアップが必要な連絡先やアプリケーションなどのオンプレミス オブジェクトが残っている場合があります。

以下の手順を使用して、これらのオブジェクトをクリーンアップし、ローカル管理者グループと RTCUniversalServerAdmins グループの両方のメンバーである必要があります。 ExUmContacts と PersistantChatEndPoints は Skype for Business Server 2019 では使用できません。 Skype for Business Server 2019 を使用している場合は、以下の手順で対応するコマンドレットを省略する必要があります。

1. Skype for Business Server のオンプレミス展開に関連付けられている連絡先またはアプリケーションが何かあるか確認するには、次の Skype for Business Server PowerShell コマンドレットを実行します。

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. 手順 1 のコマンドレットからの出力リストを確認します。 次に、オブジェクトを削除できる場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>オンプレミスの Skype for Business 展開を削除する

すべての予備的な手順を完了した後、次の手順に従って Skype for Business の展開を削除できます。

1. 次のように、1 つのフロントエンドを除き、Skype for Business Server 展開を論理的に削除します。

   a. Skype for Business Server トポロジを更新して、1 つのフロントエンド プールを使用します。

     - トポロジ ビルダーで、新しいコピーをダウンロードし、Frontend プールに移動します。
     - プールを右クリックし、[**プロパティの編集**] をクリックします。
     - [ **関連付け] で**、[ **エッジ プールの関連付け** ] (メディア コンポーネントの場合) のチェックを外し **、[OK] をクリックします**。
     - 複数のフロントエンド プールがある場合は、残りのすべてのプールの関連付けを削除します。
     - [アクション **] を選択>展開の削除] を選択します**。
     - [アクション **] を>トポロジの発行] を選択します**。

    b. トポロジを公開したら、ウィザードで説明されている追加の手順を実行します。

2. 次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server 会議ディレクトリを削除します。

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. 次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server 展開のアンインストールを完了します。

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > この手順でエラーが返される場合は、Microsoft サポート チケットを開き、残りの古いオブジェクトの削除に関するヘルプを受け取ります。

4. 次の Skype for Business Server PowerShell コマンドレットを実行して、サーバーの全体管理ストア サービスコントロール ポイントを削除します。

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. 次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server Active Directory ドメインフォレスト レベルの変更を元に戻します。

   ```PowerShell
   Disable-CsAdDomain
   ```
6. 次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server Active Directory ドメイン スキーマの変更を元に戻します。

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を使用停止する](decommission-on-prem-overview.md)

- [ユーザーとエンドポイントをクラウドに移動する](decommission-move-on-prem-users.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)














