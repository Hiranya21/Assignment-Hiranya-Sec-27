public class EqualPrefixSuffixSum {

    public static boolean canBeSplit(int[] arr) {
        int totalSum = 0;
        for (int num : arr) {
            totalSum += num;
        }

        int leftSum = 0;
        // Go until second last element to avoid empty suffix
        for (int i = 0; i < arr.length - 1; i++) {
            leftSum += arr[i];
            int rightSum = totalSum - leftSum;

            if (leftSum == rightSum) {
                return true;
            }
        }

        return false;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 6};
        boolean result = canBeSplit(arr);
        System.out.println("Can the array be split into equal prefix and suffix sums? " + result);
    }
}
