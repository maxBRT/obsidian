# for id, element := range slice

The important thing to retain is that `slice[id]` is referring  directly to the original element while `element` is creating a copy so no changes will apply to the original slice

Will modify the message:
``func tagMessages(messages []sms, tagger func(sms) []string) []sms {
``	for i, msg := range messages {
``		messages[i].tags = tagger(msg)
``	}
``	return messages
`}

Won't modify the message :
`func tagMessages(messages []sms, tagger func(sms) []string) []sms {
``	for _, msg := range messages {
``		msg.tags = tagger(msg)
``	}
``	return messages
`}

