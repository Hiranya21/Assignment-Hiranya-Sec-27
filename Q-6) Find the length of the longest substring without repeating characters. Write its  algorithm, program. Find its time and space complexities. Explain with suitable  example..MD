import java.util.HashSet;

public class LongestSubstring {

    public static int lengthOfLongestSubstring(String s) {
        HashSet<Character> seenChars = new HashSet<>();
        int maxLength = 0;
        int start = 0;

        for (int end = 0; end < s.length(); end++) {
            char currentChar = s.charAt(end);

            while (seenChars.contains(currentChar)) {
                seenChars.remove(s.charAt(start));
                start++;
            }

            seenChars.add(currentChar);
            maxLength = Math.max(maxLength, end - start + 1);
        }

        return maxLength;
    }

    public static void main(String[] args) {
        String input = "abcabcbb";
        int result = lengthOfLongestSubstring(input);
        System.out.println("Length of the longest substring without repeating characters: " + result);
    }
}
