Replacing a substring in a string

'''cpp
void replace(std::string& targetString, const std::string& oldString, const std::string& newString)
	// Unable to process if the target string or the string to replace are empty
	if (!targetString.empty() && !oldString.empty()) {
		std::string::size_type pos = targetString.find(oldString);
		for (; std::string::npos != pos; pos = targetString.find(oldString, pos)) {
			targetString.replace(pos, oldString.length(), newString);
			// Increment the position in case the the new string contains the old string (i.e. replacing 'xx' with 'yxx')
			pos += newString.length();
		}
	}
}
'''
