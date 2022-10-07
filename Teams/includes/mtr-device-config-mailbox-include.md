
リソース アカウントが会議出席依頼に対して応答し、処理する方法をカスタマイズすることで、Teams Rooms会議エクスペリエンスを向上させることができます。 Exchange Online PowerShell を使用して、次のリソース アカウントのプロパティを設定できます。

- **AutomateProcessing: `AutoAccept`** 会議の開催者は、人間の介入なしに直接会議室予約の決定を受け取ります。

- **AddOrganizerToSubject: `$false`** 会議の開催者は、会議出席依頼の件名に追加されません。

- **DeleteComments: `$false`** 受信会議出席依頼のメッセージ本文にテキストを保持します。 これは、One Touch Join エクスペリエンスを提供するために、外部 Teams とサード パーティの会議を処理するために必要です。

- **DeleteSubject: `$false`** 受信した会議出席依頼の件名を保持します。

- **ProcessExternalMeetingMessages: `$true`** Exchange 組織の外部から送信された会議出席依頼を処理するかどうかを指定します。 外部の Teams 会議と [サード パーティの会議に必要です](/microsoftteams/rooms/third-party-join)。

- **RemovePrivateProperty: `$false`** 元の会議出席依頼で会議の開催者によって送信されたプライベート フラグが指定されたとおりに保持されるようにします。

- **AddAdditionalResponse: `$true`** AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。

- **AdditionalResponse: "これは Microsoft Teams の会議室です!** 会議の承諾応答に追加する追加のテキスト。

これらのプロパティを構成するには、Exchange Online PowerShell に接続する必要があります。 詳細については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)」を参照してください。

Exchange Online PowerShell に接続したら、[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing) コマンドレットを使用してリソース アカウントのメールボックスプロパティを構成できます。

次の例では、リソース アカウントのプロパティを `ConferenceRoom01` 設定します。

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

