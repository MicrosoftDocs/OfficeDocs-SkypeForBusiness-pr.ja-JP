---
title: 'Lync Server 2013: 社内の Lync Server 2013 と Exchange Online との統合の構成'
TOCTitle: 社内の Lync Server 2013 と Exchange Online との統合の構成
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48272930
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 社内の Lync Server 2013 と Exchange Online との統合の構成

 

_**トピックの最終更新日:** 2014-07-02_

社内の Lync Server 2013 展開を使用する顧客は、ハイブリッド展開モードの Microsoft Exchange Online で、Microsoft Outlook Web App との相互運用性を構成できます。相互運用性機能には、シングル サインオンが含まれるほか、Outlook Web App インターフェイスとのインスタント メッセージングおよびプレゼンスの統合が含まれます。この統合を有効にするには、以下のタスクを完了して、 エッジ サーバーを社内の Lync Server 展開に構成する必要があります。

  - 共有 SIP アドレス スペースを構成する

  - エッジ サーバーにホスティング プロバイダーを構成する

  - 更新された 中央管理ストアのレプリケーションを確認する

## 共有 SIP アドレス スペースを構成する

社内の Lync Server 2013 を Exchange Online と統合するには、共有 SIP アドレス スペースを構成する必要があります。同じ SIP ドメイン アドレス スペースが、 Lync Server サービスおよび Exchange Online サービスでサポートされます。

Lync Server 管理シェルを使用し、次の例に示されたパラメーターを使用する **Set-CSAccessEdgeConfiguration** コマンドレットを実行して、フェデレーション用の エッジ サーバーを構成します。

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインからのユーザーと通信することを許可するかどうかを指定します。このプロパティは、内部ユーザーが Lync Server および Exchange Online を使用して、共有 SIP アドレス スペース シナリオ内のユーザーと通信できるかどうかも決定します。

Lync Server 管理シェルの使用方法については、「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」を参照してください。

## エッジ サーバーにホスティング プロバイダーを構成する

Lync Server 管理シェルを使用し、次の例に示されたパラメーターを使用する **New-CsHostingProvider** コマンドレットを実行して、 エッジ サーバーにホスティング プロバイダーを構成します。

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

> [!NOTE]
> 中国の 21Vianet により運営されている Office 365 を使用してる場合は、この例の <strong>ProxyFqdn</strong> パラメーターの値 (&quot;exap.um.outlook.com&quot;) を、21Vianet により運営されているサービスの FQDN である &quot;exap.um.partner.outlook.cn&quot; に置き換えます。


  - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値から成る識別子を指定します (例: "Exchange Online")。空白を含む値は、二重引用符で囲む必要があります。

  - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。これを True に設定する必要があります。

  - **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。これを True に設定する必要があります。

  - **HostsOCSUsers** は、 Office Communications Server または Lync Server をホストするためにホスティング プロバイダーが使用されるかどうかを示します。これを False に設定する必要があります。

  - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。Exchange Online の FQDN は exap.um.outlook.com です。

  - **IsLocal** は、ホスティング プロバイダーによって使用されるプロキシ サーバーが Lync Server トポロジ内にあるかどうかを示します。これを False に設定する必要があります。

  - **VerificationLevel** は、ホストされるプロバイダーとの間で送受信されるメッセージに対して許可される確認レベルを示します。 **UseSourceVerification** を指定します。これは、ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼します。このレベルが指定されていない場合、メッセージは、確認不能として拒否されます。

## 更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して変更した内容は、 エッジ サーバーに自動的に適用され、通常、1 分未満でレプリケートされます。以下のコマンドレットを使用して、レプリケーションの状態を検証し、変更内容が エッジ サーバーに適用されたことを確認できます。

レプリケーションの更新状況を確認するには、 Lync Server 展開の内部にあるサーバーで、次のコマンドレットを実行します。

    Get-CsManagementStoreReplicationStatus

変更が適用されたことを確認するには、 エッジ サーバーで次のコマンドレットを実行します。

    Get-CsHostingProvider -LocalStore

## 関連項目

#### その他のリソース

[Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 の Hosted Exchange ユニファイド メッセージング統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)

