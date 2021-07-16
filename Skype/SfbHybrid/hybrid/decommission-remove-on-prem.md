---
title: 使用停止Skype for Business Server
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
description: 使用停止の手順Skype for Business Server。
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454340"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>オンプレミスの Skype for Business の展開を削除する

この記事では、オンプレミスの展開を削除するSkype for Business説明します。 これは、オンプレミス環境を使用停止するための次の手順の手順 4 です。

- 手順 1. [必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。 

- 手順 2. [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- 手順 3. [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行する](decommission-move-on-prem-endpoints.md)

- **手順 4.オンプレミスの展開をSkype for Businessします。** (この記事)


> [!IMPORTANT] 
> この記事の手順は、ここで説明するように、ユーザー属性の管理に方法 2 を使用している場合にのみ適用 [されます](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。 方法 1 を使用している場合は、この記事で説明されている手順を使用してサーバーを削除Skype for Businessしてください。 代わりに、サーバーを再イメージできます。

この記事の手順を完了するには、スキーマ管理者グループと管理者グループのEnterprise必要です。 Active Directory ドメイン サービスに対するスキーマSkype for Business Serverフォレスト レベルの変更を元に戻すには、これらの特権が必要です。 RTCUniversalServerAdmins グループのメンバーである必要があります。


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>展開を削除するSkype for Businessする

必要なすべてのユーザー アカウントをクラウドに移動した後も、クリーンアップが必要な連絡先やアプリケーションなどのオンプレミス オブジェクトが残っている場合があります。

以下の手順を使用して、これらのオブジェクトをクリーンアップし、ローカル管理者グループと RTCUniversalServerAdmins グループの両方のメンバーである必要があります。 ExUmContacts と PersistantChatEndPoints は、2019 年にSkype for Business Serverしてください。 2019 Skype for Business Server場合は、以下の手順で対応するコマンドレットを省略する必要があります。

1. オンプレミスの展開に関連付けられている連絡先またはアプリケーションSkype for Business Server確認するには、次の PowerShell コマンドレットSkype for Business Server実行します。

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
2. 手順 1 のコマンドレットからの出力リストを確認します。 次に、オブジェクトを削除できる場合は、PowerShell コマンドレットSkype for Business Server実行します。

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>オンプレミスの Skype for Business の展開を削除する

すべての予備的な手順を完了した後、次の手順に従ってSkype for Business展開を削除できます。

1. 次のように、1 Skype for Business Serverを除き、展開の論理的な削除を行います。

   1. 1 つのフロントエンド Skype for Business Serverを持つトポロジを更新します。

      1. トポロジ ビルダーで、新しいコピーをダウンロードし、Frontend プールに移動します。
      1. プールを右クリックし、[**プロパティの編集**] をクリックします。
      1. [ **関連付け] で**、[ **エッジ プールの関連付け** ] (メディア コンポーネントの場合) のチェックを外し **、[OK] をクリックします**。
      1. 複数のフロントエンド プールがある場合は、残りのすべてのプールの関連付けを削除します。
      1. [アクション **] を選択>展開の削除] を選択します**。
      1. [アクション **] を>トポロジの発行] を選択します**。

    1. トポロジを公開したら、ウィザードで説明されている追加の手順を実行します。

2. 次Skype for Business Server PowerShell コマンドレットを実行して、会議ディレクトリSkype for Business Server削除します。

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. PowerShell コマンドレットを実行して、Skype for Business Server展開のアンインストールをSkype for Business Serverします。

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > この手順でエラーが返される場合は、Microsoft サポート チケットを開き、残りの古いオブジェクトの削除に関するヘルプを受け取ります。

4. PowerShell コマンドレットで次のコマンドを実行して、サーバーの全体管理ストア サービスSkype for Business Server削除します。

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. 次Skype for Business Server PowerShell コマンドレットを実行して、Active Directory ドメイン レベルのSkype for Business Server元に戻します。

   ```PowerShell
   Disable-CsAdDomain
   ```
6. 次Skype for Business Server PowerShell コマンドレットを実行して、Active Directory フォレスト レベルの変更Skype for Business Server取り消します。

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

- [必要なすべてのユーザーをオンプレミスからオンラインに移動する](decommission-move-on-prem-users.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)

- [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する](decommission-move-on-prem-endpoints.md)

